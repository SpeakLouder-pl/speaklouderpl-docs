# SpeakLouder — KB dla agenta AI (3/4): Workflow, Leady, Aktywność

> Wewnętrzna baza wiedzy dla asystenta AI (supportowo-sprzedażowego). Cel: agent zna dokładnie, gdzie i jak się co ustawia, co oznaczają statusy i jak diagnozować problemy. Odpowiedzi do użytkownika po polsku. Ten plik pokrywa: **Workflow** (`/campaigns/:id/workflow`), **Źródło leadów** (`/campaigns/:id/source`), **CRM / listę leadów** (`/campaigns/:id/leads`), **kartę leada** (`/campaigns/:id/leads/:leadId`) oraz **Aktywność** (Połączenia + Dziennik akcji). Numery, integracje, kredyty i konto — patrz plik 4.

---

## 1. Workflow / Przepływ pracy (`/dashboard/campaigns/:id/workflow`)

Nagłówek strony: **„Przepływ pracy”**. Definiuje **kiedy i jak** agent kontaktuje się z leadem (sekwencja + harmonogram) oraz **co robi automatycznie po rozmowie** (SMS, e-mail, transfer, warunek kwalifikacji, webhook).

Strona ma dwie warstwy:
1. **Sekwencja kontaktów** (osobny edytor graficzny — przycisk „Edytuj sekwencję”).
2. **Ustawienia globalne** i **Zaawansowane** — bloki z przełącznikami i formularzami, zapisywane paskiem „Zapisz zmiany”.

> **WAŻNE:** wszystkie zmiany w Workflow działają na **przyszłe** połączenia i kroki. Nie zmieniają wstecz już wykonanych ani już zaplanowanych i uruchomionych kroków dla leadów, którzy są w trakcie.

### 1.1. Sekwencja kontaktów (edytor)

Uporządkowana lista kroków wykonywanych po kolei dla każdego leada. Otwiera się przyciskiem **„Edytuj sekwencję”** (ikona ołówka). Pod przyciskiem widać podgląd (numerowana lista faz z ikonami).

**Typy węzłów (kroków):**
- `start` — Start (węzeł brzegowy, niewidoczny jako krok, dokładnie 1).
- `end` — Koniec (węzeł brzegowy „Sekwencja zakończona”, dokładnie 1).
- `call` — **Połączenie** (ikona telefonu).
- `sms` — **SMS** (ikona dymka).
- `email` — **E-mail** (ikona koperty).

Kroki środkowe (`call`/`sms`/`email`) mają domyślne nazwy **„Faza 1”, „Faza 2”, „Faza 3”…** (funkcja `defaultPhaseName` → `Faza N`, gdzie N liczone od 1). Nazwę fazy można edytować.

**Twarde limity edytora (z kodu `SCENARIO_LIMITS`):**

| Limit | Wartość | Uwaga |
|---|---|---|
| Maks. liczba węzłów łącznie (`maxNodes`) | **40** | wliczając Start/Koniec |
| Maks. kroków typu **call** (`maxCallNodes`) | **4** | najwyżej 4 próby połączenia |
| Treść **SMS w kroku sekwencji** (`smsBodyMax`) | **160 znaków** | tylko ASCII (patrz niżej) |
| Temat **e-maila** (`emailSubjectMax`) | **200 znaków** | |
| Treść **e-maila** (`emailBodyMax`) | **100 000 znaków** | praktycznie bez limitu |
| Nazwa fazy (`phaseNameMax`) | **80 znaków** | |
| Opóźnienie między krokami — min (`waitMinDelayMinutes`) | **0 minut** | |
| Opóźnienie między krokami — maks (`waitMaxDelayMinutes`) | **7200 minut = 5 dni** | |

**Opóźnienia (wait) między krokami** — na krawędziach między węzłami. Jednostki: sekundy / minuty / godziny / dni (`EdgeDelayUnit`). Domyślne wartości:
- Start → pierwszy krok: ~**10 sekund** (`DEFAULT_START_TO_FIRST_DELAY_MINUTES = 10/60`).
- Kolejny krok → następny: **5 minut** (`DEFAULT_SEQUENTIAL_EDGE_DELAY_MINUTES`).
- Do węzła Koniec: opóźnienie zawsze **0**.
Opóźnienie jest przycinane do zakresu 0–7200 min (`clampDelayMinutes`).

**Warunek przejścia** między krokami: `no_answer` („Brak odpowiedzi”) — kolejny krok wykonuje się, gdy poprzedni nie zakończył się sukcesem (np. lead nie odebrał). Sekwencja to jedna kolumna (łańcuch): każdy węzeł ma najwyżej jedno wejście i jedno wyjście.

**Walidacja przy zapisie sekwencji (`validateWorkflowForSave`) — komunikaty błędów:**
- Musi być dokładnie **1 Start i 1 Koniec** → inaczej: „Scenariusz musi mieć jeden krok Start i jeden Koniec.”
- Musi być **co najmniej 1 krok połączenia** → inaczej: „Dodaj co najmniej jeden moduł połączenia.”
- Każdy krok środkowy musi mieć **nazwę fazy** → „Każdy krok musi mieć nazwę fazy (pole „Nazwa fazy”).”
- Nazwa fazy nie może brzmieć „Start” ani „Koniec” → „Nazwa fazy nie może być „Start” ani „Koniec”. Wybierz inną nazwę.”
- Nazwy faz muszą być **unikalne** → „Dwie fazy nie mogą mieć takiej samej nazwy. Zmień jedną z nich.”
- Krok **SMS** nie może mieć pustej treści → „SMS w fazie „…” nie może być pusty. Wpisz treść wiadomości.”
- Krok **E-mail** wymaga tematu i treści → „E-mail w fazie „…” wymaga tematu i treści.”

**Domyślny scenariusz nowej kampanii:** Start → Połączenie („Pierwszy kontakt”) → SMS („Przypomnienie SMS”) → Połączenie („Druga próba”) → Koniec.

**Normalizacja SMS do ASCII (`normalizeSmsBodyForScenario`):** polskie znaki zamieniane na łacińskie (ą→a, ć→c, ę→e, ł→l, ń→n, ó→o, ś→s, ź→z, ż→z i wielkie litery), a wszystkie pozostałe znaki spoza ASCII (emoji itp.) są **usuwane**. Powód: poprawna, tania segmentacja SMS. To dlatego SMS-y wychodzą bez „ogonków”.

### 1.2. Harmonogram połączeń (blok `wf-harmonogram`)

Sekcja **„Harmonogram połączeń”** — kiedy agent może dzwonić.
- **Okno czasowe** — dwa pola typu godzina „od–do”. Domyślnie **09:00–18:00**.
- **Dni aktywne** — przyciski **Pon (1), Wt (2), Śr (3), Czw (4), Pt (5), Sob (6), Nd (7)**. Domyślnie zaznaczone Pon–Pt (1–5). Nie da się odznaczyć ostatniego zaznaczonego dnia (min. 1 dzień).

**Walidacja przy zapisie harmonogramu:**
- Musi być zaznaczony **co najmniej jeden dzień** → „Wybierz co najmniej jeden dzień dzwonienia.”
- Okno musi trwać **co najmniej 1 godzinę** (koniec − start ≥ 60 min) → „Okno połączeń musi trwać co najmniej 1 godzinę.”

**Konsekwencje:** połączenia poza oknem godzinowym i poza zaznaczonymi dniami **się nie odbywają** — agent czeka do najbliższego dozwolonego terminu. Kolumny bazy: `workflow_call_window_start`, `workflow_call_window_end`, `workflow_call_weekdays`.

### 1.3. SMS po zakwalifikowaniu (blok `wf-sms`, „Ustawienia globalne”)

Automatyczny SMS wysyłany do leada **po tym, jak agent uzna go za zainteresowanego (zakwalifikowany)**. Włącza się przełącznikiem w rozwijanej karcie.
- Pole **„Treść SMS”** z podświetlaniem placeholderów `{{…}}`.
- Licznik: **X / 500 znaków** — ten SMS po kwalifikacji ma limit **500 znaków** (uwaga: to inny limit niż krok SMS w sekwencji, który ma 160 znaków).
- **Tylko ASCII** — emoji i polskie znaki są automatycznie zamieniane (jak wyżej).
- Walidacja: przy włączonym SMS treść nie może być pusta → „Treść SMS nie może być pusta.”
- Kolumny bazy: `post_answer_call_sms_enabled`, `post_answer_call_sms_template`.

**Zmienne dynamiczne `{{…}}` dostępne w SMS/e-mailu po rozmowie** (blok „Zmienne dynamiczne (kliknij, aby skopiować)”). Rdzeń zawsze dostępny + pola własne kampanii + aliasy SMS:

| Placeholder | Znaczenie |
|---|---|
| `{{full_name}}` | Imię i nazwisko |
| `{{email}}` | E-mail |
| `{{phone_number}}` | Telefon |
| `{{first_name}}` | Imię (osobna kolumna) |
| `{{last_name}}` | Nazwisko (osobna kolumna) |
| `{{imie_i_nazwisko}}` | Alias SMS: imię i nazwisko |
| `{{imie}}` | Alias SMS: imię |
| `{{nazwisko}}` | Alias SMS: nazwisko |
| `{{nazwa_firmy}}` | Nazwa firmy (z metadanych) |
| `{{telefon}}` | Alias SMS: telefon |
| `{{<klucz_pola_własnego>}}` | Dowolne pole własne z field_schema (CSV/webhook), np. `{{product_name}}` |

Uwaga: `{{metadata}}` jest **przestarzałe** i niepodpowiadane; `{{lead_id}}` i `{{followup_workflow_action_id}}` to klucze routingowe (nie do treści). Aliasy SMS (`imie`, `nazwisko`, …) są aktywne szczególnie dla treści SMS.

### 1.4. E-mail po zakwalifikowaniu (blok `wf-email`)

Spersonalizowany e-mail follow-up wysyłany po zakwalifikowaniu leada.
- **Wymaga podłączonego Gmaila** — pole „źródło wysyłki (Gmail)” (`EmailSourceSelect`). Gmaila podłącza się w **Integracjach** (plik 4).
- Pola: **Temat** (placeholder `{{full_name}}` itp.) i **Treść** (HTML, z placeholderami).
- Przyciski: **„Podgląd HTML”** (renderuje temat + treść z przykładowymi danymi leada w sandboksowanym iframe) i **„Wyślij testowy”** (dialog „Wyślij testowy e-mail” — podajesz adres odbiorcy).
- Walidacja przy włączonym e-mailu: „Wybierz źródło wysyłki (Gmail).”, „Temat e-maila nie może być pusty.”, „Treść e-maila nie może być pusta.”
- Wysyłka testowa idzie przez edge `gmail-send-test-email`. Możliwe komunikaty błędów:
  - `gmail_disconnected` → „Wybrane konto Gmail wygasło — połącz je ponownie.”
  - `gmail_not_connected` → „Wybierz źródło Gmail w sekcji e-maila.”
  - `invalid_email` → „Niepoprawny adres e-mail.”
  - `subject_and_html_body_required` → „Uzupełnij temat i treść e-maila.”
- Kolumny bazy: `post_answer_call_email_enabled`, `post_answer_call_email_subject`, `post_answer_call_email_body`, `post_answer_call_email_source_id`.

### 1.5. Transfer do handlowca (blok `wf-handoff`)

„Czy agent ma przekazywać zakwalifikowanego leada do handlowca **podczas trwającej rozmowy**?”
- Tryb (`handoff_mode`): domyślnie `email_summary` (bez transferu, tylko podsumowanie); włączenie przełącznika ustawia `warm_transfer` (transfer na żywo).
- Przy transferze pole **„Numer do przekazania”** (`handoff_transfer_phone`, format np. `+48 600 000 000`). Agent połączy leada z tym numerem w momencie potwierdzenia zainteresowania.
- Walidacja: numer musi być poprawny → „Podaj poprawny numer do przekazania.”

### 1.6. Własny warunek zakwalifikowania (blok `wf-custom`, „Zaawansowane”)

Pole tekstowe (do **200 znaków**), w którym własnymi słowami opisujesz, kiedy lead ma być uznany za zakwalifikowanego.
- **Zastępuje wbudowaną ocenę zainteresowania AI** (info w UI: „Własny warunek zastępuje wbudowaną ocenę zainteresowania.”).
- Przykład: „Klient zgodził się na umówienie spotkania w ciągu najbliższych 7 dni i podał preferowany termin.”
- Walidacja: przy włączeniu treść nie może być pusta → „Treść warunku nie może być pusta.”
- Kolumny bazy: `custom_success_filter_enabled`, `custom_success_filter_condition`.

### 1.7. Webhook po połączeniu (blok `wf-webhook`)

Po **każdym zakończonym połączeniu** wysyła dane rozmowy do zewnętrznego systemu przez **HTTP POST** (Make / Zapier / własny CRM).
- Pole **„URL webhooka”** — musi zaczynać się od `https://…` (walidacja: „Podaj poprawny adres URL webhooka (https://…).”).
- Przyciski: **„Wyślij testowe zdarzenie”** (edge `test-post-call-webhook`; sukces gdy HTTP 2xx) i **„Wyświetl schemat payloadu”**.
- Kolumny bazy: `post_call_webhook_enabled`, `post_call_webhook_url`.

**Schemat payloadu webhooka po połączeniu (POST, JSON):**
```json
{
  "lead_id": "uuid",
  "full_name": "Jan Kowalski",
  "email": "jan@example.com",
  "phone_number": "+48 600 000 000",
  "lead_status": "qualified",
  "metadata": {},
  "transcript": "agent: …\nuser: …",
  "ai_summary": "Podsumowanie z agenta."
}
```

### 1.8. Zapisywanie zmian

Bloki mają swoje własne paski „Zapisz zmiany / Anuluj” (pod sekcją), a dodatkowo na dole ekranu wyświetla się **globalny pasek „Masz niezapisane zmiany”** (Zapisz zmiany / Anuluj). Przy błędzie walidacji strona przewija do pierwszej błędnej sekcji i pokazuje toast. Sukces: „Zapisano zmiany”.

---

## 2. Źródło leadów (`/dashboard/campaigns/:id/source`)

Nagłówek: **„Źródło”**. Typ źródła (`kind`) jest ustalony przy tworzeniu kampanii i decyduje, który wariant się wyświetla:
- `static_csv` → **Import CSV**
- `dynamic_webhook` → **Webhook HTTP**
- `shopify_abandoned_cart` → **Połączenie ze Shopify** (porzucone koszyki)
- `dynamic_meta_forms` → **Meta Lead Ads**

### 2.1. CSV Upload (`static_csv`)

Nagłówek „Import CSV”. Strefa upuszczania: **„Upuść plik CSV tutaj”** / „lub kliknij, aby przeglądać pliki” / przycisk **„Przeglądaj pliki”** (akceptuje tylko `.csv`).

> **Wymóg: kampania musi być ZATRZYMANA (wstrzymana), aby wgrać CSV.** Gdy jest aktywna, widać żółty banner „Kampania jest aktywna — Zatrzymaj kampanię, aby wgrać leady z pliku CSV.”, a strefa jest zablokowana. Próba upuszczenia pliku daje toast: „Zatrzymaj kampanię, aby wgrać leady z pliku CSV.”

**Przebieg importu (`CsvImportView`):**
1. Plik jest wczytywany jako tekst (UTF-8) i parsowany → nagłówki + wiersze. Pusty plik (brak nagłówka lub brak wierszy) → „Plik nie zawiera danych (potrzebny wiersz nagłówka + co najmniej jeden wiersz).”
2. **Mapowanie kolumn** — dla każdej kolumny wybierasz rolę:
   - **Imię i nazwisko** (`full_name`) — **wymagane**
   - **Email** (`email`) — **wymagane**
   - **Telefon** (`phone`) — **wymagane**
   - **Pole własne** (`custom`) — dodatkowe pole; podajesz jego „klucz” (slug: małe litery/cyfry/podkreślnik)
   - **Pomiń kolumnę** (`skip`)
   Auto-mapowanie próbuje odgadnąć role z nagłówków. Każde wymagane pole musi być przypisane do **dokładnie jednej** kolumny (duplikat → „Każde wymagane pole przypisz do jednej kolumny.”; brak → „Zmapuj pola: …”).
3. **Sprawdzaj duplikaty** (checkbox, domyślnie zaznaczony) — pomija leady już istniejące w tej kampanii **po numerze telefonu**. W obrębie pliku duplikaty telefonów są pomijane zawsze.
4. **Podstawa prawna kontaktu** (checkbox, **wymagany**) — oświadczenie RODO/Prawo telekomunikacyjne. Bez zaznaczenia przycisk importu jest nieaktywny.
5. Import partiami (chunk). Pasek postępu „Importowanie… X/Y”.
6. Wynik: „Import zakończony — Zaimportowano N leadów · pominięto X duplikatów · odrzucono Y błędnych.”; przy błędach lista do 5 przykładowych odrzuconych wierszy (numer wiersza + powód).

Po imporcie zapisywane jest mapowanie kolumn (`csv_column_mapping`) i schemat pól (`field_schema`), więc kolejne importy pamiętają układ.

**Dobre praktyki:** najpierw mały plik testowy (2–3 rekordy) → sprawdź mapowanie i czy lead wpadł poprawnie → potem cała lista. Upewnij się, że numery są w formacie międzynarodowym (`+48…`).

### 2.2. HTTP Webhook (`dynamic_webhook`)

Nagłówek „Webhook HTTP — Wysyłaj leady w czasie rzeczywistym żądaniem POST.” Trzy kroki:

**Krok 1 — Adres webhooka.** Gotowy URL z **tokenem** w środku:
```
https://<projekt>.supabase.co/functions/v1/leads-webhook?token=<TOKEN_KAMPANII>
```
Wysyłasz na ten adres **POST** z JSON-em. Token identyfikuje kampanię — jest już wpisany w URL. Osobne pole „Token” pokazuje go **zamaskowanego** (pierwsze 8 znaków + kropki); można go odsłonić (ikona oka) i skopiować.

> **Bezpieczeństwo tokena:** traktować jak hasło. Kto ma token, może dodawać leady do kampanii. Nie publikować w kodzie front-endu ani publicznie. W razie wycieku zgłoś do supportu (rotacja tokena).

Przycisk **„Integracja Make.com”** — link zapraszający do instalacji aplikacji SpeakLouder w Make.

**Krok 2 — Pola własne.** Definiujesz dodatkowe dane leada (Klucz + Typ). Typy: **Tekst** (`string`) lub **Liczba** (`number`). Klucz: tylko małe litery, cyfry i podkreślnik (spacje, emoji, polskie znaki są zamieniane automatycznie). Pola własne trafiają do obiektu `metadata` i są dostępne agentowi w rozmowie oraz jako placeholdery `{{klucz}}`.

**Klucze zarezerwowane (nie mogą być polem własnym):** `full_name`, `email`, `phone`, `phone_number`, `metadata`, `leads`, `campaign_id`. Próba użycia → „Klucz „…” jest zarezerwowany.” Duplikat klucza → „Klucz „…” jest zduplikowany.”

**Pola rdzeniowe payloadu:** `full_name`, `email`, `phone_number`. Reszta w `metadata`.

**Przykładowy payload (POST, JSON):**
```json
{
  "full_name": "Anna Kowalska",
  "email": "anna@example.com",
  "phone_number": "+48600123456",
  "metadata": {
    "product_name": "Kurs online",
    "budget": 1500
  }
}
```
Pole liczbowe puste → zapisywane jako `0`; niepoprawna liczba → zostaje tekstem.

**Krok 3 — Wyślij testowy lead.** Formularz (Imię i nazwisko, Email, Telefon + pola własne) buduje na żywo podgląd „Ciało żądania (JSON)”. Przycisk **„Wyślij testowy lead”** robi realny POST na webhook — **lead trafia naprawdę na listę leadów** (zwraca `lead_id`). Toast sukcesu: „Testowy lead zapisany”. Jeśli serwer odrzuci → „Serwer odrzucił testowy payload” z opisem błędu.

### 2.3. Shopify (`shopify_abandoned_cart`)

„Połączenie ze Shopify” — porzucone koszyki trafiają jako leady z listą produktów. Kampania zbiera nazwy produktów w jednym polu `product_names` (rozdzielone przecinkami) — ustawiane automatycznie. Pięć kroków z grafikami:
1. Zainstaluj aplikację **Shopify Flow** i wróć do niej z panelu Shopify.
2. Pobierz **plik Flow od nas** i zaimportuj w Shopify (przycisk „Importuj” w prawym górnym rogu). W kroku pokazany jest **adres webhooka kampanii** (ten sam co przy Webhook HTTP).
3. Wejdź w zaimportowany workflow → „Edytuj”.
4. Znajdź moduł **„Send HTTP request”**, w polu URL zastąp `WKLEJTOKEN` **tokenem** kampanii (pokazany + kopiowanie), zatwierdź „Zastosuj zmiany”.
5. **Włącz workflow** w Shopify (jeśli nieaktywny) i potwierdź.

### 2.4. Meta Forms (`dynamic_meta_forms`)

„Meta Lead Ads” — leady z formularzy Facebook/Instagram importowane automatycznie. W tym widoku informacja „Skonfiguruj integrację Meta na stronie Integracje” + przycisk „Przejdź do Integracji”. W praktyce integracja Meta jest oznaczona **„Wkrótce”** (patrz plik 4).

---

## 3. CRM / Lista leadów (`/dashboard/campaigns/:id/leads`)

Nagłówek: **„CRM”**. Lista wszystkich leadów kampanii. Podtytuł pokazuje liczbę (np. „124 leadów w tej kampanii” albo „N wyników” przy aktywnym filtrze/szukaniu).

**Kolumny tabeli:**
- **Lead** — awatar (inicjały), imię/nazwa, odznaka statusu.
- **Połączenia** (`callAttempts`) — liczba prób połączeń.
- **Ostatnia aktywność** — data + „ile temu”.
- Menu (⋯) na końcu wiersza: **Szczegóły**, **Usuń leada**.

**Narzędzia nad tabelą:**
- **Wyszukiwarka** „Szukaj leadów…” (debounce 300 ms, szuka po stronie serwera).
- **Filtruj** (popover) — po statusie (wielokrotny wybór; licznik aktywnych filtrów). „Wyczyść”.
- **Sortuj** — pola: **Imię i nazwisko** (`name`), **Liczba połączeń** (`callAttempts`), **Ostatnia aktywność** (`lastActivity`); rosnąco/malejąco.
- **Paginacja** — **10 leadów na stronę** (`PAGE_SIZE = 10`), pobieranie serwerowe.
- **Zaznaczanie** (checkboxy) — zaznaczenie trzyma się między stronami. Przy zaznaczonych: **Eksportuj** (CSV lub XLSX) i **Usuń (N)** (bulk). Usunięcie jest nieodwracalne (dialog potwierdzenia).

### 3.1. PEŁNA tabela statusów leada (`LeadStatus`)

| Kod wewnętrzny | Etykieta PL | Kolor | Znaczenie |
|---|---|---|---|
| `New` | **Nowy** | szary | Lead dodany, sekwencja jeszcze nie ruszyła / brak akcji. Ustawia się też po **restarcie workflow**. |
| `InProgress` | **W toku** | niebieski | Sekwencja aktywna, agent pracuje nad leadem. **Stan automatyczny — nie da się ustawić ręcznie.** |
| `Qualified` | **Zakwalifikowany** | zielony | Lead uznany za zainteresowanego (sukces). |
| `Disqualified` | **Niezakwalifikowany** | czerwony | Lead niezainteresowany / odrzucony. |
| `NoContact` | **Bez kontaktu** | bursztynowy | Nie udało się porozmawiać (brak odpowiedzi po wszystkich próbach). |

Kolejność w selektach/filtrach: New → InProgress → Qualified → Disqualified → NoContact.

---

## 4. Karta leada (`/dashboard/campaigns/:id/leads/:leadId`)

Trzy kolumny: lewa (dane + akcje), środek (zakładki), prawa (statystyki + akcje).

### 4.1. Lewa kolumna

- **Powrót** „Leady”.
- **Awatar z pierścieniem zainteresowania** — kolor pierścienia zależy od % z ostatniej rozmowy: **≥80 zielony, ≥50 bursztynowy, <50 czerwony**; brak danych = pierścień pusty.
- **Nazwa** + **odznaka statusu** (klik = rozwijane menu zmiany statusu).
- **Szybkie akcje (4 przyciski):**
  - **Notatka** — dodaj notatkę ręczną.
  - **Email** — wyślij e-mail (dialog: wybór konta Gmail + temat + treść). Nieaktywne, gdy lead nie ma adresu e-mail.
  - **Zadzwoń** — ręczne połączenie na żądanie (`callNow`). Nieaktywne, gdy brak numeru **lub gdy ręczne połączenie już wykonano** (`onDemandCalls >= 1`, tooltip „Ręczne połączenie zostało już wykonane”) lub trwa wywołanie.
  - **Więcej** — menu: **Edytuj dane**, **Zmień status**, **Restartuj workflow** (planuje sekwencję od nowa), **Usuń leada**.
- **Tagi** — Dodaj/Edytuj; **max 5 tagów** na leada. Tagi tworzy się w Ustawienia → Tagi.
- **Kluczowe dane** — Email (mailto), Telefon (tel), Dodano (data).
- **Zainteresowanie leada** — pasek 0–100 z ostatniej rozmowy. „brak danych” gdy nie było rozmowy; „Pojawi się po pierwszej rozmowie z leadem.”
- **Następny krok** (jeśli jest) — „Aktywny/Zaplanowany”, nazwa i termin.

**Zmiana statusu ręcznie:** możliwe wartości do wyboru to **Zakwalifikowany, Niezakwalifikowany, Bez kontaktu** (`SELECTABLE_STATUSES`). „Nowy” ustawia się przez **restart workflow**; „W toku” jest automatyczny (próba ustawienia → „„W toku” to stan automatyczny — ustawia się sam, gdy scenariusz jest aktywny.”). Mapowanie na backend:
- Zakwalifikowany → outcome `qualified`
- Niezakwalifikowany → outcome `not_interested`
- Bez kontaktu → outcome `no_contact`
- Nowy → restart workflow

> **Ustawienie statusu końcowego (Qualified/Disqualified/NoContact) anuluje wszystkie zaplanowane akcje** dla tego leada (dialog: „Ustawienie statusu końcowego anuluje wszystkie zaplanowane akcje dla tego leada.”).

### 4.2. Środek — zakładki

- **Pulpit** — na górze **„Analiza AI”** (podsumowanie ostatniej rozmowy generowane przez AI; notatki AI z poczty głosowej są ukrywane jako bezużyteczne), pod spodem **Notatki** ręczne (dodawanie/edycja/usuwanie).
- **Dane** — „Dane z formularza”: wszystkie pola leada, w tym pola własne ze źródła (pytanie → odpowiedź). „Brak danych z formularza.” gdy pusto.
- **Sekwencja** — „Sekwencja kampanii”: lista kroków z osi czasu. Link „Edytuj workflow”. Każdy krok: „Krok N” (lub „Ręczne” dla połączeń poza sekwencją), typ (Połączenie/SMS/Email), odznaka statusu, ewentualne zainteresowanie %, czas długości rozmowy, znaczniki „SMS/E-mail po rozmowie”, czas wykonania/planu. Sekcja **„Poza sekwencją”** grupuje połączenia ręczne. Przy połączeniach: „Szybki podgląd” i „Szczegóły” (deep-link do Aktywność → Połączenia z daną rozmową).
  - **Statusy/odznaki kroku:** „Anulowano” (cancelled), „Pominięto” (skipped — z powodem, patrz sekcja 6), „Ukończono”, „W toku” (dialing/awaiting_outcome), „Zaplanowane”, oraz wyniki połączeń (Odebrane / Brak odpowiedzi / Poczta głosowa / SMS wysłany / E-mail wysłany).
  - Wyniki „pozytywne”: `completed`, `sms_sent`, `email_sent`, `sent`.
  - Podpowiedzi „w toku”: `dialing` → „Inicjujemy połączenie wychodzące…”; `awaiting_outcome` → „Połączenie wystartowało. Po rozłączeniu zapiszemy wynik rozmowy.”
- **Wysłane emaile** — historia e-maili do leada. Każdy: temat, „Do/z”, rodzaj (**Ręczny** = `manual`, **Sekwencja** = `sequence`, **Po rozmowie** = `post_call`), data, status **Wysłany** (`sent`) lub **Błąd**, oraz treść w ramce.

### 4.3. Prawa kolumna

- **Statystyki** (4 kafelki): **Połączenia** (liczba prób), **SMS-y** (kroki SMS ukończone + SMS-y po rozmowie), **Emaile** (kroki e-mail ukończone + e-maile po rozmowie), **Odebrane** (zakończone rozmowy niebędące pocztą głosową).
- **Ostatnie akcje** — chronologiczna lista zdarzeń leada (call/sms/email/webhook), z odznaką wyniku; przy follow-upie dopisek „po kwalifikacji”.

### 4.4. „Zainteresowanie leada” — jak działa

To **ocena AI (0–100)** wystawiana automatycznie na podstawie treści rozmowy — jak bardzo lead jest zainteresowany. Aktualizowana po każdej rozmowie (pokazujemy z ostatniej). **Nie jest polem do ręcznego wpisania.** Próg kwalifikacji: **50** (`QUALIFIED_THRESHOLD`) — od 50 lead traktowany jako zakwalifikowany. Jeśli włączony jest „Własny warunek zakwalifikowania”, to on zastępuje tę ocenę.

---

## 5. Aktywność

### 5.1. Połączenia (`/dashboard/campaigns/:id/activity/calls`)

Nagłówek „Połączenia”. Układ dwukolumnowy (lista + szczegóły).

**Lista (lewa):**
- Wyszukiwarka „Szukaj leada…” (debounce 300 ms).
- **Sortowanie:** Najnowsze (`created_desc`, domyślnie), Najstarsze, Najdłuższe, Najkrótsze, Najwyższe zainteresowanie.
- **Filtr zakładkami:** **Wszystkie** / **Zakwalifikowany** (interest ≥ 50) / **Niezakwalifikowany** (interest < 50).
- Każda pozycja: nazwa leada, data, kierunek (Przychodzące/Wychodzące), długość, odznaka zainteresowania %, skrót podsumowania.
- Paginacja serwerowa.

**Panel szczegółów (prawa) dla zaznaczonej rozmowy:**
- **Lead** (+ „Otwórz leada”), **Telefon**.
- **Rozmowa:** **kierunek** (Przychodzące = inbound / Wychodzące = outbound), **wynik** (`answered`→Odebrane, `failed`→Nieudane, `callback_requested`→Prośba o oddzwonienie), **długość**, **% zainteresowania**.
- **Data**.
- **Oddzwonienie** (jeśli lead prosił): „Zaplanowano oddzwonienie: <data>” lub „Klient prosił o oddzwonienie”.
- **Nagranie** — link „Odsłuchaj nagranie” (jeśli dostępne).
- **Po kwalifikacji** (tylko dla zakwalifikowanych): odznaki „SMS wysłany/wyłączony”, „E-mail wysłany/wyłączony” — zależnie od włączonych automatyzacji w Workflow.
- **Podsumowanie** (AI) — tekst.
- **Transkrypcja** — dymki „Klient” (po lewej) i „Agent” (po prawej); jeśli brak turn, tekst ciągły; „Brak transkrypcji dla tej rozmowy.” gdy pusto.

Deep-link: z karty leada „Szczegóły” połączenia otwiera tę stronę z `?conversation=<id>` i od razu zaznacza rozmowę.

### 5.2. Dziennik akcji (`/dashboard/campaigns/:id/activity/action-log`)

Nagłówek „Dziennik akcji — Wykonane akcje w tej kampanii.” Chronologiczna lista wszystkich zdarzeń.
- Typy: **Połączenie** (call), **SMS**, **E-mail**, **Webhook**, **Akcja** (other). Follow-up → dopisek „po kwalifikacji”.
- Każdy wiersz: ikona typu, „<typ> do <lead>”, odznaka wyniku, data-godzina. Klik w nazwisko → **karta leada**.
- **Filtr po dacie** (pole daty w prawym górnym rogu; „×” czyści).
- Paginacja. Pusto: „Brak akcji” / „Brak akcji w wybranym dniu”.

---

## 6. Powody pominięcia kroku (skip_reason) — PEŁNA tabela

Surowych kodów **nie pokazujemy klientowi** — UI mapuje je na czytelny tytuł + opis (`formatSkipReason`). Nieznany kod snake_case → generyczny „Krok pominięty”.

| Kod (`skip_reason`) | Tytuł (PL) | Komunikat | Co powiedzieć / zrobić |
|---|---|---|---|
| `client_callback_scheduled` | Oddzwonienie umówione z klientem | Klient poprosił o oddzwonienie o wyznaczonej godzinie — ten krok został anulowany. | To normalne. Agent oddzwoni o umówionej porze (wymaga włączonego „Oddzwaniania” u agenta). |
| `below_interest_threshold` | Krok anulowany | Lead nie spełnia progu zainteresowania — krok pominięty. | Lead miał zbyt niskie zainteresowanie (<50 lub niespełniony własny warunek). Można ręcznie zmienić status/zrestartować. |
| `lead_closed` | Krok anulowany | Lead jest zamknięty — pozostałe kroki nie będą wykonane. | Lead ma status końcowy. Aby wznowić kontakt: restart workflow. |
| `manual_restart` | Krok anulowany | Scenariusz zrestartowano ręcznie — ten krok nie jest już aktualny. | Ktoś zrestartował workflow — stare kroki zastąpione nowymi. |
| `manual_status` | Krok anulowany | Status leada ustawiono ręcznie — pozostałe kroki anulowane. | Status końcowy ustawiono ręcznie → reszta anulowana (oczekiwane). |
| `inbound_callback_win` | Krok anulowany | Oddzwonienie inbound zakończyło się sukcesem — kolejne kroki niepotrzebne. | Lead sam oddzwonił i rozmowa się udała — dalsze próby zbędne. |
| `voicemail` | Pominięto | Wykryto pocztę głosową. | Trafiono na automat — SMS/e-mail po rozmowie pominięte (brak realnej rozmowy). |
| `interest_too_low` | Pominięto | Zbyt niskie zainteresowanie klienta. | Jak `below_interest_threshold` — lead poniżej progu. |
| `insufficient_credits` | Pominięto | Niewystarczające środki. | **Doładuj kredyty** (Ustawienia → Kredyty), potem krok wykona się przy kolejnej próbie. |
| `no_phone` | Pominięto | Brak numeru telefonu. | Uzupełnij numer w karcie leada (Edytuj dane) — bez numeru nie zadzwonimy. |
| `no_email` | Pominięto | Brak adresu e-mail. | Uzupełnij e-mail leada (Edytuj dane) — inaczej e-mail follow-up się nie wyśle. |

---

## 7. FAQ / Troubleshooting

1. **„Dlaczego krok w sekwencji jest Anulowany/Pominięty?”** — Sprawdź powód pod krokiem (tabela w sekcji 6). Najczęściej: status końcowy leada (manual/lead_closed), zbyt niskie zainteresowanie, brak kredytów, brak numeru/e-maila, poczta głosowa lub restart workflow.

2. **„Czemu lead ma status Bez kontaktu?”** — Nie udało się z nim porozmawiać po wszystkich zaplanowanych próbach połączeń (nie odbierał / poczta głosowa). To nie błąd. Można zrestartować workflow lub zadzwonić ręcznie (przycisk „Zadzwoń”).

3. **„Jak działa kwalifikacja leada?”** — Po rozmowie AI wystawia ocenę zainteresowania 0–100. Od **50** lead jest zakwalifikowany. Jeśli w Workflow włączysz „Własny warunek zakwalifikowania”, ocena AI zostaje zastąpiona Twoim opisem sukcesu.

4. **„Jak dodać pole własne (webhook)?”** — Źródło → Webhook HTTP → krok 2 „Pola własne”: Dodaj pole, wpisz klucz (małe litery/cyfry/podkreślnik) i typ (Tekst/Liczba), „Zapisz pola”. Pole trafi do `metadata` i będzie dostępne jako `{{klucz}}` oraz agentowi w rozmowie. Uwaga na klucze zarezerwowane.

5. **„Mój webhook nie dodaje leadów — jak zdiagnozować?”** — Kolejno: (a) **URL i token** — czy używasz dokładnie adresu ze strony Źródło z aktualnym tokenem? (b) **Metoda** — musi być **POST**, nagłówek `Content-Type: application/json`. (c) **Format** — poprawny JSON z `full_name`, `email`, `phone_number` (+ `metadata`). (d) **Test** — użyj przycisku „Wyślij testowy lead” na stronie Źródło; jeśli tam działa, problem jest po stronie nadawcy (Make/CRM). (e) Sprawdź odpowiedź serwera — komunikat błędu wskaże, czego brakuje.

6. **„Nie mogę wgrać CSV.”** — Kampania musi być **zatrzymana**. Zatrzymaj ją (Dashboard kampanii → „Zatrzymaj kampanię”), wgraj plik, potem wznów. Sprawdź też, że plik ma wiersz nagłówka + co najmniej jeden wiersz danych i zmapowane są 3 wymagane pola (imię i nazwisko, email, telefon) oraz zaznaczone oświadczenie o podstawie prawnej.

7. **„SMS wyszedł bez polskich znaków / bez emoji.”** — Tak działa celowo: treść SMS jest **tylko ASCII** — polskie znaki są zamieniane na łacińskie, a emoji usuwane (dla poprawnej i taniej segmentacji SMS). Dotyczy zarówno SMS w sekwencji, jak i SMS po zakwalifikowaniu.

8. **„Jaki jest limit znaków SMS?”** — SMS w kroku sekwencji: **160 znaków**. SMS po zakwalifikowaniu (Ustawienia globalne): **500 znaków**. Oba tylko ASCII.

9. **„Jak zmienić status leada ręcznie?”** — Karta leada → klik w odznakę statusu (lub Więcej → Zmień status) → wybierz Zakwalifikowany/Niezakwalifikowany/Bez kontaktu. „Nowy” = przez „Restartuj workflow”. „W toku” nie da się ustawić ręcznie. Uwaga: status końcowy anuluje zaplanowane akcje.

10. **„Gdzie znajdę transkrypcję i nagranie rozmowy?”** — Aktywność → Połączenia → zaznacz rozmowę: po prawej „Podsumowanie”, „Transkrypcja” i link „Odsłuchaj nagranie” (jeśli jest). Można też wejść z karty leada: zakładka Sekwencja → przy połączeniu „Szczegóły”.

11. **„E-mail follow-up się nie wysłał.”** — Wymaga: (a) włączonej opcji „E-mail po zakwalifikowaniu” w Workflow, (b) wybranego **źródła Gmail** (podłączonego w Integracjach; jeśli wygasł → połącz ponownie), (c) leada z adresem e-mail (inaczej `no_email`), (d) zakwalifikowania leada. Sprawdź też zakładkę „Wysłane emaile” na karcie leada — status „Błąd” wskazuje problem z wysyłką.

12. **„Agent nie dzwoni w ogóle.”** — Sprawdź: kampania Aktywna (nie Wstrzymana), przypisany numer, wystarczające kredyty, oraz **harmonogram** — czy jesteśmy w oknie godzinowym i w zaznaczonym dniu tygodnia. Poza oknem agent czeka.

13. **„Zmieniłem workflow, ale lead nadal idzie starą ścieżką.”** — Zmiany działają na przyszłe połączenia i nowe/zrestartowane leady. Aby zastosować nową sekwencję do konkretnego leada od zera: karta leada → Więcej → **Restartuj workflow**.

14. **„Jak przekazać rozmowę do handlowca?”** — Workflow → „Transfer do handlowca” → włącz → podaj poprawny numer. Agent przełączy zakwalifikowanego leada na ten numer podczas rozmowy.

15. **„Jak wysłać dane rozmowy do mojego CRM/Make/Zapier?”** — Workflow → „Webhook po połączeniu” → włącz, wklej URL `https://…`, „Wyślij testowe zdarzenie” do sprawdzenia. Po każdej rozmowie dostaniesz POST z `lead_id`, danymi leada, `lead_status`, `metadata`, `transcript`, `ai_summary`.

16. **„Ile prób połączenia mogę ustawić?”** — Maksymalnie **4 kroki typu Połączenie** w sekwencji. Między nimi możesz wstawić SMS/e-mail i ustawić opóźnienia (do 5 dni).

17. **„Czy mogę mieć dwie fazy o tej samej nazwie?”** — Nie. Nazwy faz muszą być unikalne i różne od „Start”/„Koniec”. Inaczej zapis sekwencji się nie powiedzie.

18. **„Testowy lead z webhooka zapisał się realnie — jak go usunąć?”** — Tak, testowy lead trafia na listę. Usuń go: CRM → menu (⋯) przy leadzie → „Usuń leada” (lub zaznacz i użyj „Usuń (N)”).

19. **„Dlaczego nie widzę zainteresowania (brak danych)?”** — Ocena pojawia się dopiero **po pierwszej realnej rozmowie** z leadem. Przed rozmową (lub gdy trafiono na pocztę głosową) pokazuje „brak danych”.

20. **„Nie mogę kliknąć Zadzwoń na karcie leada.”** — Przycisk jest jednorazowy: ręczne połączenie na żądanie można wykonać **raz** (tooltip „Ręczne połączenie zostało już wykonane”). Wymaga też numeru telefonu leada.

21. **„Jak wyeksportować leady?”** — CRM → zaznacz leady → „Eksportuj” → wybierz **CSV** lub **Excel (.xlsx)** → „Pobierz”.

22. **„Ile leadów widzę na stronie?”** — 10 na stronę (paginacja serwerowa). Wyszukiwarka i filtry działają na całej kampanii, nie tylko na bieżącej stronie.

23. **„Zmieniłem token webhooka / wyciekł — co robić?”** — Token to hasło do dodawania leadów. Zgłoś do supportu (dostęp: Ustawienia → Konto → „Dostęp pomocy technicznej”) w celu rotacji i zaktualizuj adres w Make/CRM/Shopify.

24. **„Import CSV odrzucił część wierszy.”** — Na ekranie wyniku widać liczbę odrzuconych + do 5 przykładów z numerem wiersza i powodem (np. brak/niepoprawny numer telefonu, brak wymaganego pola). Popraw dane w pliku i wgraj ponownie. Duplikaty (po telefonie) są pomijane, nie odrzucane.

---

### Nawigacja powiązana
- Konfiguracja agenta, prompt, głos, „Oddzwanianie”, narzędzia (kalendarz) → **plik 2**.
- Numery telefonów, Integracje (Make, Gmail, kalendarz), kredyty/cennik, weryfikacja KYB, ustawienia konta → **plik 4**.
- Podstawy, logowanie, mapa URL-i → **plik 1**.
