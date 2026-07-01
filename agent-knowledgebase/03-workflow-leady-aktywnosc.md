# SpeakLouder — KB dla agenta AI (3/4): Workflow, Leady, Aktywność

## Workflow / Przepływ pracy (`/campaigns/:id/workflow`)

Definiuje, kiedy i jak agent kontaktuje się z leadem oraz co robi po rozmowie.

### Sekwencja kontaktów

Uporządkowana lista kroków wykonywanych po kolei dla każdego leada. Typy kroków (węzłów): **call** (połączenie), **sms**, **email** (plus wewnętrzne start/end). Przycisk **Edytuj sekwencję** pozwala zmieniać kolejność, dodawać i usuwać kroki. Kroki mają domyślne nazwy „Faza 1", „Faza 2"… (edytowalne).

Limity edytora sekwencji:
- maksymalnie **4 kroki typu call**,
- SMS w kroku: do **160 znaków**,
- temat e-maila: do **200 znaków**, treść e-maila: bardzo duży limit,
- opóźnienie między krokami (wait): od 0 minut do **5 dni**,
- nazwa fazy: do 80 znaków.

### Harmonogram połączeń

- **Okno czasowe** — godziny „od–do", w których agent może dzwonić.
- **Dni aktywne** — dni tygodnia (Pon–Nd) do zaznaczenia.
Połączenia poza oknem/dniami się nie odbywają. Zmiany zapisuje **Zapisz zmiany**.

### Automatyzacje po rozmowie (Ustawienia globalne)

Każda ma przełącznik wł/wył; po rozwinięciu wiersza — szczegóły:
- **SMS po zakwalifikowaniu** — automatyczny SMS, gdy agent uzna leada za zainteresowanego. Pole „Treść SMS" (do ~500 znaków, **tylko ASCII** — polskie znaki i emoji są zamieniane). Dostępne **zmienne dynamiczne** do wklejenia, m.in. `{{full_name}}`, `{{email}}`, `{{phone_number}}`, `{{first_name}}`, `{{last_name}}` oraz pola własne ze źródła.
- **E-mail po zakwalifikowaniu** — spersonalizowany e-mail follow-up. Wymaga podłączonego Gmaila (poczta wychodząca) w Integracjach.
- **Transfer do handlowca** — przekazanie rozmowy na żywo do handlowca w trakcie połączenia.

### Zaawansowane

- **Własny warunek zakwalifikowania** — pole tekstowe (do ~200 znaków), w którym własnymi słowami opisujesz, kiedy lead ma być uznany za zakwalifikowanego. **Zastępuje** domyślną ocenę zainteresowania AI.
- **Webhook po połączeniu** — po każdej rozmowie wysyła dane połączenia do zewnętrznego systemu przez HTTP POST (integracja z Make, Zapier lub własnym CRM).

## Źródło leadów (`/campaigns/:id/source`)

Typ źródła jest ustalony przy tworzeniu kampanii; tutaj się go konfiguruje.

### CSV Upload
Nagłówek „Import CSV". Strefa **„Upuść plik CSV tutaj"** lub **Przeglądaj pliki** (akceptuje `.csv`). Po wgraniu następuje mapowanie kolumn pliku na pola leada. **Uwaga:** aby wgrać CSV, kampania musi być **zatrzymana** (jest komunikat „Zatrzymaj kampanię, aby wgrać leady z pliku CSV"). Rekomendacja: najpierw mały plik testowy, sprawdzić mapowanie, potem cała lista.

### HTTP Webhook
Nagłówek „Webhook HTTP". Zawiera:
1. **Adres webhooka** — gotowy URL z **tokenem** identyfikującym kampanię (token jest już wpisany w URL; osobne pole „Token" pokazuje go zamaskowanego). Wysyła się na ten adres żądanie **POST** z danymi leada. Token traktować jak hasło — nie ujawniać publicznie.
2. **Pola własne** — dodatkowe dane (klucz + typ, np. Tekst) przekazywane agentowi razem z leadem, zapisywane w `metadata`.
3. Przycisk **Integracja Make.com** — ułatwia połączenie z Make.

Struktura payloadu (rdzeń): `full_name`, `email`, `phone_number`; dodatkowe pola idą do `metadata`. Klucze zarezerwowane (nie mogą być polem własnym): `full_name`, `email`, `phone`, `phone_number`, `metadata`, `leads`, `campaign_id`.

### Shopify
Po podłączeniu integracji agent automatycznie dzwoni do klientów, którzy porzucili koszyk.

### Meta Forms
Import z reklam Facebook/Instagram — **Wkrótce**, niedostępne.

## CRM (`/campaigns/:id/leads`)

Lista wszystkich leadów kampanii z wyszukiwarką, filtrem i sortowaniem. Kolumny: Lead (imię + status), Połączenia, Ostatnia aktywność.

### Statusy leada (wewnętrzne → etykieta PL)
- `New` → **Nowy**
- `InProgress` → **W toku**
- `Qualified` → **Zakwalifikowany** (zielony)
- `Disqualified` → **Niezakwalifikowany** (czerwony)
- `NoContact` → **Bez kontaktu** (bursztynowy) — nie udało się porozmawiać (brak odpowiedzi)

## Karta leada (`/campaigns/:id/leads/:leadId`)

- **Lewa kolumna:** awatar, nazwa, status (klik zmienia status), szybkie akcje — **Notatka**, **Email**, **Zadzwoń** (nieaktywne, jeśli ręczne połączenie już wykonano), **Więcej**. Dalej: **Tagi** (Dodaj/Edytuj), **Kluczowe dane** (email, telefon, data dodania), pasek **Zainteresowanie leada** 0–100.
- **Środek — zakładki:**
  - **Pulpit** — **Analiza AI** ostatniej rozmowy + **Notatki**.
  - **Dane** — wszystkie pola leada, w tym pola własne ze źródła.
  - **Sekwencja** — „Sekwencja kampanii": kroki (KROK 1, 2…) ze statusami (np. Brak odpowiedzi, Anulowano, Zaplanowano na…), typem (Połączenie/Email) i przyciskiem **Szczegóły**; osobno „Poza sekwencją" — połączenia ręczne (np. Odebrane, zainteresowanie %, długość). Link **Edytuj workflow**.
  - **Wysłane emaile** — historia e-maili follow-up.
- **Prawa kolumna:** **Statystyki** (Połączenia, SMS-y, Emaile, Odebrane) i **Ostatnie akcje**.

**Zainteresowanie leada** to ocena AI na podstawie treści rozmów (0–100), aktualizowana po każdej rozmowie — nie jest polem do ręcznego wypełnienia.

## Aktywność

### Połączenia (`/campaigns/:id/activity/calls`)
Widok dwukolumnowy. Lewa: lista rozmów z filtrem **Wszystkie / Zakwalifikowany / Niezakwalifikowany** i wyszukiwarką. Prawa (dla zaznaczonej rozmowy): lead + telefon, **kierunek** (Wychodzące/Przychodzące), **wynik** (Odebrane / Brak odpowiedzi), długość, % pewności, data; „Po kwalifikacji" (np. „SMS wysłany", „E-mail wyłączony"); **Podsumowanie** (AI) i **Transkrypcja** (dymki agent/klient). „Otwórz leada" prowadzi do karty.

### Dziennik akcji (`/campaigns/:id/activity/action-log`)
Chronologiczna lista wszystkich zdarzeń kampanii (połączenia, SMS-y, e-maile) z wynikiem i datą. Filtr daty w prawym górnym rogu. Klik w nazwisko → karta leada.

## Powody pominięcia kroku (skip reasons) — do interpretacji dla użytkownika

Surowych kodów nie pokazujemy klientowi; mapowanie na czytelny komunikat:
- `client_callback_scheduled` → „Oddzwonienie umówione z klientem" — klient poprosił o oddzwonienie, krok anulowany.
- `below_interest_threshold` / `interest_too_low` → lead nie spełnia progu zainteresowania — krok pominięty.
- `lead_closed` → lead zamknięty — pozostałe kroki nie będą wykonane.
- `manual_restart` → scenariusz zrestartowano ręcznie.
- `manual_status` → status ustawiono ręcznie — pozostałe kroki anulowane.
- `inbound_callback_win` → udane oddzwonienie inbound — kolejne kroki niepotrzebne.
- `voicemail` → wykryto pocztę głosową.
- `insufficient_credits` → niewystarczające środki (kredyty).
- `no_phone` → brak numeru telefonu leada.
- `no_email` → brak adresu e-mail leada.
