# SpeakLouder — KB dla agenta AI (2/4): Kampanie i Agent

> Wewnętrzna baza wiedzy dla asystenta AI (supportowo-sprzedażowego). Opisuje sekcję kampanii i agenta w panelu SpeakLouder (https://app.speaklouder.pl). Język odpowiedzi do użytkownika: polski. Skróty i pojęcia podstawowe — patrz plik 1; workflow, leady i aktywność — plik 3; numery, integracje, kredyty, konto — plik 4.

Ten plik ma odpowiadać na WSZYSTKO z obszaru „kampanie + agent": gdzie się co klika, jak krok po kroku, co wybrać, jak to sprzedać i jak rozwiązać najczęstsze problemy.

---

## 1. Lista kampanii (`/dashboard/campaigns`)

To główny ekran zarządzania kampaniami. Wchodzi się z menu po lewej („Kampanie") lub z Przeglądu.

### Podsumowanie u góry (4 karty KPI)

- **Wszystkie kampanie** — liczba wszystkich kampanii, pod spodem „X aktywnych".
- **Wykonane połączenia** — łącznie we wszystkich kampaniach.
- **Łączne leady** — wszystkie leady, pod spodem „X zakwalifikowanych".
- **Śr. skuteczność** — procent: zakwalifikowani / wszyscy leady (0% jeśli brak leadów).

### Tabela „Wszystkie kampanie"

Kolumny: **Kampania** (nazwa), **Typ** (źródło leadów), **Status** (badge), **Leady** (liczba), **Akcje** (przycisk **Szczegóły**). Cały wiersz jest klikalny — klik gdziekolwiek albo w „Szczegóły" wchodzi do kampanii (`/dashboard/campaigns/:id`, który przekierowuje do „Pierwsze kroki"). Gdy brak kampanii — „Brak kampanii"; w trakcie ładowania — „Ładowanie…".

### Statusy kampanii (wewnętrzne → etykieta PL + kolor badge)

| Status wewn. | Etykieta na liście | Etykieta na dashboardzie kampanii | Kolor | Znaczenie |
|---|---|---|---|---|
| `Active` | **Aktywna** | Aktywna | zielony | Agent dzwoni zgodnie z workflow. |
| `Paused` | **Wstrzymana** | **Zatrzymana** | bursztynowy | Kampania istnieje, ale agent nie dzwoni. |
| `Completed` | Zakończona | Zakończona | niebieski | Kampania zakończona. |
| `Draft` | Szkic | Szkic | szary | Wersja robocza. |

> Uwaga językowa dla supportu: na liście status `Paused` = „Wstrzymana", a na dashboardzie tej samej kampanii = „Zatrzymana". To ta sama rzecz — kampania nie dzwoni.

### Jak przełączać się między kampaniami

W lewym górnym rogu (wewnątrz kampanii) jest rozwijana lista do szybkiego skoku między kampaniami — nie trzeba wracać na listę. Poza kampanią wracasz do listy przez „Kampanie" w menu.

---

## 2. Tworzenie kampanii — krok po kroku

Start: przycisk **Nowa kampania** (u góry listy kampanii lub w menu po lewej). Menu kieruje na `/dashboard/campaigns?new=1`, co samo otwiera ten sam modal, co przycisk na liście.

### Krok 1 — modal „Wybierz typ kampanii"

Siatka 2×2 kafelków. **Typ kampanii decyduje wyłącznie o źródle leadów** — nie o agencie ani cenniku. Wybierasz jeden kafelek i klikasz **Dalej** (przycisk nieaktywny, dopóki nic nie wybrano). „Anuluj" zamyka.

Dostępne typy (dokładnie jak w panelu):

| Typ w UI | Opis w panelu | `kind` w bazie | Dostępny? |
|---|---|---|---|
| **HTTP Webhook** | „Przesyłaj leady przez żądanie JSON HTTP z dowolnego systemu." | `dynamic_webhook` | Tak |
| **Shopify** | „Automatycznie docieraj do klientów z porzuconymi koszykami." | `shopify_abandoned_cart` | Tak |
| **CSV Upload** | „Wgraj arkusz kalkulacyjny, aby masowo zaimportować leady." | `static_csv` | Tak |
| **Meta Forms** | „Importuj leady z reklam na Facebooku i Instagramie." | `dynamic_meta_forms` | **Wkrótce** (nieaktywny) |

#### HTTP Webhook — kiedy wybrać, dla kogo, plusy/minusy

- **Kiedy:** gdy leady mają wpadać **automatycznie i na bieżąco** z zewnętrznego systemu przez żądanie POST (formularz na stronie, Make.com, Zapier, własny backend/CRM).
- **Dla kogo:** firmy z formularzem kontaktowym/landing page, agencje, integratorzy, każdy kto chce dzwonić do leada „w kilka sekund po zgłoszeniu".
- **Plusy:** natychmiastowość (im szybszy kontakt, tym wyższa konwersja), pełna automatyzacja, elastyczne pola własne przekazywane agentowi.
- **Minusy:** wymaga jednorazowego skonfigurowania po stronie źródła (URL webhooka + token).
- **Scenariusz sprzedażowy:** „Klient zostawia numer na landing page → w 10 sekund oddzwania agent AI, kwalifikuje i umawia spotkanie. Zero czekania, zero utraconego leada." Konfiguracja webhooka — patrz plik 3 (Źródło leadów).

#### Shopify — kiedy wybrać

- **Kiedy:** sklep na Shopify chce **odzyskiwać porzucone koszyki** telefonicznie.
- **Dla kogo:** e-commerce (Shopify), które traci sprzedaż na etapie checkoutu.
- **Plusy:** w pełni automatyczne — po podłączeniu integracji agent sam dzwoni do klientów z porzuconym koszykiem; wysoki potencjał ROI (odzyskany koszyk = konkretny przychód).
- **Minusy:** tylko Shopify (inne platformy — na razie przez HTTP Webhook).
- **Scenariusz sprzedażowy:** „Klient dodał produkty za 600 zł i nie dokończył. Agent dzwoni, pyta czy pomóc dokończyć zamówienie, proponuje wsparcie/rabat. Odzyskujesz sprzedaż, która i tak by przepadła."

#### CSV Upload — kiedy wybrać

- **Kiedy:** masz **gotową listę** kontaktów (arkusz), jednorazowy lub okresowy import.
- **Dla kogo:** kampanie do bazy (reaktywacja klientów, cold/warm calling z listy, ankiety).
- **Plusy:** najprostszy start — wgrywasz plik i dzwonisz; pełna kontrola nad listą.
- **Minusy:** import ręczny; **aby wgrać CSV kampania musi być zatrzymana** (patrz plik 3); to nie jest strumień „na żywo".
- **Scenariusz sprzedażowy:** „Masz 2000 starych klientów w Excelu? Wrzuć plik, ustaw prompt reaktywacyjny i w jeden dzień agent obdzwoni całą listę z ofertą powrotu."

#### Meta Forms — Wkrótce

Leady z reklam Lead Ads na Facebooku/Instagramie. Kafelek jest oznaczony „Wkrótce" i **nieklikalny**. Do czasu premiery leady z Meta można wpuszczać przez HTTP Webhook + Make.com. Nie obiecuj daty — mów „w przygotowaniu".

### Krok 2 — „Nazwij kampanię"

Po „Dalej" pojawia się drugi ekran z podglądem wybranego typu (ikona + opis) i polem **Nazwa kampanii** (placeholder „np. Kampania nieruchomości Q3"). Przyciski: **Wróć** (do wyboru typu) i **Utwórz kampanię** (nieaktywny przy pustej nazwie; Enter też tworzy). Podczas tworzenia przycisk pokazuje „Tworzenie…". Po utworzeniu trafiasz od razu na **Pierwsze kroki** tej kampanii.

> Wskazówka: typu kampanii nie da się później zmienić — wybór źródła jest „na wejściu". Jeśli klient pomylił typ, najprościej utworzyć nową kampanię.

---

## 3. Pierwsze kroki kampanii (`/campaigns/:id/get-started`)

Ekran onboardingu kampanii z powitaniem („Witaj, {imię}! 👋") i checklistą 7 kart. Każda karta to link do właściwej zakładki.

| # | Karta | Opis w panelu | Prowadzi do |
|---|---|---|---|
| 1 | **Skonfiguruj agenta** | „Ustaw głos i styl rozmowy." | `…/agent` |
| 2 | **Ustaw workflow** | „Zbuduj scenariusz kampanii." | `…/workflow` |
| 3 | **Przetestuj agenta** | „Porozmawiaj z agentem w przeglądarce." | `…/agent?testagent=1` (otwiera od razu popup testu) |
| 4 | **Podłącz źródło leadów** | „Zaimportuj kontakty do kampanii." | `…/source` |
| 5 | **Przypisz numer telefonu** | „Wybierz numer w zakładce numeru." | `…/phone` |
| 6 | **Uruchom kampanię** | „Włącz kampanię i zacznij dzwonić." | `…/dashboard` |
| 7 | **Doładuj kredyty** | „Zadbaj o kredyty na połączenia." | `/dashboard/settings?tab=billing` |

### Sekcja „Potrzebujesz pomocy?" (3 karty)

- **Porozmawiaj z asystentem** — otwiera panel asystenta AI (ten sam ✨ z górnego paska).
- **Umów spotkanie z ekspertem** — link do Cal.com (`cal.com/speaklouder/30min`); „Bezpłatnie pomożemy skonfigurować kampanię."
- **Otwórz dokumentację** — poradniki i FAQ.

Checklista pozostaje widoczna także po ukończeniu konfiguracji — to punkt odniesienia. Do bieżącej pracy z kampanią służy zakładka **Dashboard**.

Rekomendowana kolejność dla nowego użytkownika: **1 → 2 → 3 (test) → 4 → 5 → 6**, a kredyty (7) w dowolnym momencie przed startem.

---

## 4. Warunki uruchomienia kampanii (`campaign-start-guard`)

Kampania **nie zadzwoni**, dopóki nie są spełnione dwa twarde warunki. Przy kliknięciu „Uruchom kampanię" system sprawdza je i — jeśli brakuje — zamiast startu otwiera odpowiedni dialog prowadzący do rozwiązania.

1. **Przypisany numer telefonu.** Bez numeru → dialog **„Przypisz numer telefonu"**: „Ta kampania nie ma przypisanego numeru, z którego agent dzwoni do leadów. Przypisz numer, żeby ją uruchomić." Przycisk **Przejdź do numeru** prowadzi do ustawień kampanii (tam wybiera się numer). (Zakup/przypisanie numeru wymaga zweryfikowanej firmy — patrz plik 4.)
2. **Wystarczające kredyty.** Próg = **najtańsza operacja w scenariuszu** (minimum ze stawek SMS i połączenia głosowego). Gdy saldo < próg → dialog **„Za mało kredytów"**: „Potrzebujesz co najmniej {próg} kredytów (najtańsza operacja w scenariuszu), aby uruchomić kampanię. Doładuj saldo w zakładce Kredyty." Przycisk **Doładuj kredyty** → `/dashboard/settings?tab=billing`.

Dodatkowo, **przy pierwszym uruchomieniu** kampanii pojawia się jednorazowy popup **„Podstawa prawna kontaktu z leadami"** — checkbox, w którym użytkownik oświadcza, że ma podstawę prawną (zgodę lub uzasadniony interes) do kontaktu telefonicznego i SMS ze wszystkimi leadami tej kampanii i ponosi odpowiedzialność jako administrator danych. Przycisk **Potwierdź i uruchom**. Zaznaczenie zapisuje się raz na kampanię — przy kolejnych startach już nie pyta.

Jest też krótki **cooldown** (~1,4 s) między przełączeniami start/stop — chroni przed przypadkowym „miganiem" statusu. Jeśli przycisk chwilę nie reaguje po kliknięciu — to normalne.

---

## 5. Dashboard kampanii (`/campaigns/:id/dashboard`)

Bieżący widok operacyjny jednej kampanii.

### Nagłówek

Nazwa kampanii + badge statusu (Aktywna / Zatrzymana). Po prawej przycisk akcji:
- Gdy **Aktywna** → **Zatrzymaj kampanię** (czerwony). Klik otwiera dialog „Zatrzymać kampanię?" z ostrzeżeniem: „Spowoduje to anulowanie wszystkich zaplanowanych akcji dla tej kampanii." Potwierdzenie przyciskiem **Zatrzymaj kampanię**.
- Gdy **Zatrzymana** → **Uruchom kampanię** (zielony). Klik przechodzi przez guardy (numer + kredyty + oświadczenie o podstawie prawnej) z sekcji 4.

### KPI (4 karty)

- **Wszystkie leady** — liczba leadów; pod spodem „+X w tym tygodniu" (nowe z ostatnich 7 dni) lub „Brak nowych w tym tygodniu".
- **Zakwalifikowane** — liczba; pod spodem „X% wszystkich leadów".
- **Wskaźnik kwalifikacji** — procent (zakwalifikowani / wszyscy).
- **Liczba połączeń** — suma prób połączeń w kampanii.

### Wykres „Aktywność kampanii"

Wykres warstwowy z ostatnich **14 dni**: dzienny wolumen **leadów** i **zakwalifikowanych** (po dacie dodania leada). „Dzienny wolumen leadów i zakwalifikowanych".

### „Ostatnia aktywność"

Lista do 5 leadów wg ostatniego kontaktu/zmiany: nazwa + status (etykieta PL) + „ile temu". Gdy pusto — „Brak aktywności". Pełna historia — w zakładce Aktywność (plik 3).

---

## 6. Zakładka Agent (`/campaigns/:id/agent`) — wyczerpująco

To „serce" kampanii: jak agent brzmi i co mówi. Zakładka Agent = konfiguracja agenta (dawniej `agent/configuration`). Numer telefonu przeniesiono do ustawień kampanii.

### 6.1. Kreator dla nowej kampanii (onboarding agenta)

Gdy kampania **nie ma jeszcze własnego promptu** (prompt = domyślny) i użytkownik go nie pominął, zamiast pustych pól pokazuje się pełnoekranowy kreator.

- **Ekran startowy:** logo + nagłówek **„Skonfigurujmy Twojego agenta"** i opis: „Odpowiedz na kilka pytań o kampanii, a AI przygotuje gotowe prompty i pierwsze wypowiedzi dla rozmów przychodzących i wychodzących." Przycisk **Zacznij konfigurację**.
- **Pytania (styl typeform):** jedno pytanie na ekran, licznik **„Pytanie X z N"**. Pytania dobierane są pod typ kampanii (webhook/CSV/Shopify). Typy pól: tekst, pole długie, wybór jednokrotny, „Inne" z własną odpowiedzią. Nawigacja: **Dalej**, **Wstecz**, a przy pytaniach opcjonalnych **Pomiń pytanie**. Ostatni krok to przycisk **Skonfiguruj agenta** (z ikoną ✨).
- **Pominięcie kreatora:** w prawym górnym rogu zawsze jest **„Pomiń i skonfiguruj ręcznie →"** — przechodzi od razu do widoku edycji z domyślnymi promptami. Pominięcie/ukończenie zapisuje się per kampania (nie wraca przy każdym wejściu).
- **Co robi AI po ostatnim pytaniu:** ekran „Konfigurujemy Twojego agenta…" w dwóch fazach: (1) „AI pisze prompty i pierwsze wypowiedzi na podstawie Twoich odpowiedzi" (generacja), (2) „Zapisujemy konfigurację i synchronizujemy agenta głosowego" (zapis + utworzenie/aktualizacja agentów). Efekt: gotowe **osobne** prompty i pierwsze wypowiedzi dla rozmów **przychodzących** i **wychodzących**.
- **Zakończenie:** „Agent gotowy! Prompty zostały wygenerowane i zapisane. Możesz je w każdej chwili dopracować w „Zarządzaj promptem"." Przycisk **Zakończ**.
- **Błąd:** ekran „Nie udało się skonfigurować" z opcjami **Zakończ** i **Spróbuj ponownie**. Jeśli się powtarza — sprawdź sesję (przeloguj) i spróbuj później; ewentualnie skonfiguruj ręcznie.

### 6.2. Widok po konfiguracji

Nagłówek: nazwa kampanii + „Konfiguracja agenta głosowego". Po prawej trzy przyciski (opis w 6.3). Poniżej sekcje:

#### Głos

Pokazuje aktualny głos (awatar, nazwa, opis) z dwoma akcjami: ikona **głośnika** („Odsłuchaj próbkę" aktualnego głosu) i **Zmień**. „Zmień" otwiera modal **„Wybierz głos agenta"**: „Odsłuchaj próbki i wybierz głos, którym agent będzie rozmawiał z leadami." Siatka kart głosów — każda z nazwą, tagami (kategoria + region), krótkim opisem i przyciskiem **Odsłuchaj próbkę**. Zaznaczasz kartę, klikasz **Zapisz głos** (albo „Anuluj"). 

- Głosy pochodzą z kuratorowanej listy dla regionu (polskie głosy, męskie i żeńskie, o różnym charakterze — spokojny/energiczny, formalny/ciepły). Dokładna lista i próbki są w modalu — zawsze odsyłaj użytkownika do odsłuchania, bo brzmienie to kwestia gustu i grupy docelowej.
- **Zapis głosu jest natychmiastowy** i od razu synchronizuje agenta (toast „Głos zapisany i zsynchronizowany"). Nie trzeba nic więcej klikać.
- **Jak dobierać:** głos dopasuj do odbiorcy i branży (np. spokojny/ciepły do klienta indywidualnego, rzeczowy do B2B). Odsłuchaj 2–3 próbki, potem zapisz.

#### Konfiguracja promptu

Krótka karta „Wychodzące i przychodzące" z przyciskiem **Zarządzaj**, który otwiera pełny edytor promptu (patrz 6.4). To tu mieszkają instrukcje agenta — **osobno** dla połączeń wychodzących i przychodzących.

#### Oddzwanianie

Przełącznik (Włączone/Wyłączone). Gdy **włączone**, a klient w trakcie rozmowy poprosi o kontakt w innym terminie i poda godzinę — agent sam zaplanuje i wykona oddzwonienie, bez ręcznego ustawiania w workflow. Zapis jest natychmiastowy (z resynchronizacją agenta); switch jest chwilowo zablokowany na czas zapisu.

#### Narzędzia (kalendarz)

„Daj agentowi dostęp do narzędzi, np. kalendarza, aby umawiał spotkania podczas rozmowy." Pokazuje status: „Brak podłączonego kalendarza" lub nazwę podłączonego kalendarza (np. „Cal.com · typ wydarzenia").
- Jeśli **nie ma** połączonego kalendarza na koncie → przycisk **Przejdź do integracji** (`/dashboard/integrations`). Kalendarz łączy się raz na konto w Integracjach (patrz plik 4).
- Jeśli **jest** → przycisk **Wybierz** otwiera dialog „Wybierz kalendarz" z opcją „Bez kalendarza" i listą połączonych kalendarzy. Wybór zapisuje przycisk **Wybierz** (toast „Kalendarz podłączony do agenta").

#### Baza wiedzy — **Wkrótce**

Sekcja oznaczona „Wkrótce", nieaktywna: „Udostępnij agentowi dokumenty, które wykorzysta podczas rozmów. Funkcja będzie dostępna wkrótce." Na razie wiedzę o ofercie wpisujemy wprost do promptu.

### 6.3. Górne przyciski zakładki Agent

- **Testuj agenta** (ikona ▶) — rozmowa testowa w przeglądarce, **bez zużywania kredytów** (patrz 6.5).
- **Wyślij połączenie** (ikona telefonu) — testowe połączenie **na żywo** na wskazany numer (patrz 6.6).
- **Zarządzaj promptem** (ikona ołówka) — pełny edytor treści promptu (6.4).

### 6.4. Edytor promptu — „Konfiguracja agenta" (przycisk Zarządzaj / Zarządzaj promptem)

Duży dwupanelowy dialog.

**Lewy panel — edytor.** Zakładki **Przychodzące** / **Wychodzące**, każda z dwoma polami:
- **Pierwsza wypowiedź** — pierwsze zdanie agenta (dla inbound to powitanie po odebraniu; dla outbound to zagajenie po połączeniu).
- **System prompt** — pełne instrukcje agenta.

Dla zakładki **Wychodzące** nad polami pokazują się dostępne **placeholdery** `{{...}}` (np. `{{full_name}}`, pola własne ze źródła) — wstawiasz je do treści, a agent podstawi realne dane leada w rozmowie. **Zakładka Przychodzące nie używa placeholderów** (agent nie zna z góry, kto dzwoni).

**Prawy panel — „Asystent AI".** Najpierw krótki **wywiad** (te same pytania co w kreatorze); po zakończeniu AI generuje/aktualizuje prompty, a dalej można rozmawiać po ludzku: „skróć powitanie", „dodaj pytanie o budżet", „bądź bardziej bezpośredni" — AI przepisuje prompty na bieżąco. Przy każdej odpowiedzi asystenta jest **„Cofnij do tutaj"** (przywraca poprzednią wersję promptów i skraca historię). Gdy agent jest już skonfigurowany, wywiad jest pomijany — od razu tryb edycji.

Przyciski dialogu:
- **Zapisz i przetestuj** — zapisuje, synchronizuje agenta i od razu otwiera panel testu głosowego.
- **Zacznij od nowa** — czyści historię czatu (prompty zostają bez zmian).
- **Zapisz i zsynchronizuj** (główny) — zapisuje i synchronizuje; toast „Zapisano · Konfiguracja została zsynchronizowana."
- **Anuluj / X** — zamyka; przy niezapisanych zmianach pojawia się „Nie zapisane zmiany · Czy na pewno chcesz wyjść?".

> Ważne: sam wpis w polach **nie działa**, dopóki nie klikniesz „Zapisz i zsynchronizuj" (albo „Zapisz i przetestuj"). Dopiero zapis tworzy/aktualizuje agenta głosowego.

### 6.5. „Testuj agenta" — rozmowa w przeglądarce (bez kosztów)

Popup z rozmową głosową przez przeglądarkę. Najpierw ekran **„Co chcesz przetestować?"** z dwoma kafelkami:
- **Agent dzwoni do klienta** (tryb wychodzący) — „Agent sam dzwoni do leadów. Tak działa kampania wychodząca." (domyślnie zaznaczony, bo większość kampanii jest wychodząca).
- **Klient dzwoni do agenta** (tryb przychodzący) — „Agent odbiera, gdy lead zadzwoni na Twój numer."

Każdy kafelek ma badge **„Gotowy do testu"** (zielony) albo **„Nie skonfigurowany"** (bursztynowy — trzeba najpierw zapisać danego agenta w edytorze).

Po wyborze: dla trybu wychodzącego można uzupełnić **dane leada** (pola z placeholderów; „Imię i nazwisko" bywa wymagane). Klik **Rozpocznij rozmowę** → przeglądarka prosi o **mikrofon** (trzeba zezwolić), agent zaczyna mówić. Można też pisać wiadomości tekstem. „Zmień typ testu" wraca do wyboru. **Ten test nie zużywa kredytów** — idealny do dopracowania promptu przed startem.

### 6.6. „Wyślij połączenie" — test na żywo

Dialog **„Wyślij połączenie testowe"**. Wymaga, aby kampania miała **przypisany numer** — bez niego komunikat „Ta kampania nie ma jeszcze przypisanego numeru telefonu. Przypisz numer w ustawieniach kampanii…". Pola:
- **Agent:** Przychodzący / Wychodzący (jeśli dany agent nie jest zapisany — podpowiedź „Najpierw zapisz agenta … (Konfiguracja promptu → Zarządzaj)").
- **Numer telefonu** (wymagany, walidowany — np. `+48 600 700 800`).
- Dla trybu wychodzącego — **pola danych leada** (wszystkie wymagane).
- **Oświadczenie (checkbox, wymagane):** „Oświadczam, że numer należy do mnie lub osoby, która wyraziła zgodę. Nadużycie … może skutkować odpowiedzialnością prawną i blokadą konta."

Przycisk **Zadzwoń**. Po zainicjowaniu: „Połączenie zainicjowane · Agent … zaraz zadzwoni na podany numer. Odbierz, aby przetestować rozmowę." To jest **prawdziwe połączenie telefoniczne** (przez numer kampanii) — używaj do finalnego sprawdzenia jakości na żywo. Do zwykłego dopracowania promptu wystarczy „Testuj agenta" w przeglądarce (bez kosztów).

---

## 7. Praktyczny przewodnik pisania promptu (dla użytkownika)

Prompt to instrukcja dla agenta: kim jest, po co dzwoni/odbiera, jak ma mówić i kiedy uznać leada za „gotowego". W SpeakLouder prompt jest **osobny dla rozmów wychodzących i przychodzących** — warto dopracować oba.

### Struktura dobrego promptu (system prompt)

1. **Rola i firma** — kim jest agent, jaką firmę reprezentuje, czym firma się zajmuje.
2. **Cel rozmowy** — jeden, konkretny: umówić spotkanie / potwierdzić zainteresowanie / dokończyć zamówienie / zebrać informacje.
3. **Ton i styl** — np. „mów krótko, ciepło, po polsku; nie naciskaj; nie przerywaj". Krótkie zdania brzmią naturalniej.
4. **Przebieg** — 3–5 kroków rozmowy (zagajenie → 1–2 pytania kwalifikujące → propozycja następnego kroku → domknięcie).
5. **Kwalifikacja** — po czym poznać, że lead jest zainteresowany (to steruje statusem „Zakwalifikowany"; własny warunek można też ustawić w Workflow — plik 3).
6. **Obsługa obiekcji** — 2–3 typowe wątpliwości i gotowe, krótkie odpowiedzi.
7. **Granice** — czego agent NIE robi/nie obiecuje (ceny spoza oferty, gwarancje, dane wrażliwe).

### Zasady „pierwszej wypowiedzi"

- **Outbound:** krótko się przedstaw, powiedz skąd dzwonisz i zapytaj, czy to dobry moment. Personalizuj imieniem przez `{{first_name}}`/`{{full_name}}`.
- **Inbound:** ciepłe powitanie + pytanie „w czym mogę pomóc?". Bez placeholderów.

### Przykłady — połączenia WYCHODZĄCE (outbound)

**Przykład A — umawianie spotkań (B2B / usługi):**
> Pierwsza wypowiedź: „Dzień dobry, z tej strony Ala z firmy {{company}}. Dzwonię w sprawie zgłoszenia, które zostawił Pan/Pani na naszej stronie. Czy to dobry moment na chwilę rozmowy?"
>
> System prompt (fragment): „Jesteś konsultantką {{company}}. Cel: umówić 20-minutowe spotkanie online z ekspertem. Zadaj maksymalnie dwa pytania kwalifikujące: (1) czego szuka rozmówca, (2) kiedy chce to wdrożyć. Jeśli jest zainteresowany — zaproponuj konkretny termin i potwierdź. Mów krótko, naturalnie, nie naciskaj. Obiekcja „nie mam czasu" → zaproponuj krótszy, dogodny termin. Obiekcja „za drogo" → podkreśl korzyść i zaproponuj rozmowę z ekspertem, nie podawaj cen spoza oferty."

**Przykład B — reaktywacja z listy (CSV):**
> Pierwsza wypowiedź: „Dzień dobry {{first_name}}, dzwonię z {{company}} — mamy dla Pana/Pani ofertę powrotu. Ma Pan/Pani chwilę?"
>
> System prompt (fragment): „Cel: sprawdzić, czy klient jest zainteresowany powrotem i przekazać ofertę. Jeśli tak — potwierdź zainteresowanie i zapowiedz SMS ze szczegółami. Jeśli nie — podziękuj i zakończ uprzejmie. Nie dzwoń natrętnie, jedna propozycja."

**Przykład C — porzucony koszyk (Shopify):**
> Pierwsza wypowiedź: „Dzień dobry, dzwonię ze sklepu {{company}} — widzę, że zaczął Pan/Pani zamówienie i coś przeszkodziło. Mogę pomóc je dokończyć?"
>
> System prompt (fragment): „Cel: pomóc dokończyć zakup. Zapytaj, czy był problem techniczny lub pytanie o produkt. Rozwiej wątpliwość, zaproponuj pomoc/wsparcie. Nie obiecuj rabatów, których nie ma w ofercie."

### Przykłady — połączenia PRZYCHODZĄCE (inbound)

**Przykład D — infolinia / kwalifikacja:**
> Pierwsza wypowiedź: „Dzień dobry, w czym mogę pomóc?"
>
> System prompt (fragment): „Jesteś uprzejmym asystentem {nazwa firmy}. Ustal cel rozmówcy, odpowiedz na pytania o ofertę zwięźle i — jeśli rozmówca jest zainteresowany — umów kolejny krok (spotkanie/oddzwonienie handlowca). Mów po polsku, krótko i naturalnie."

### Gotowy szablon system promptu (do skopiowania i uzupełnienia)

Poniższy szkielet działa dla większości kampanii wychodzących — wystarczy podmienić pola w nawiasach:

> „Jesteś [rola, np. konsultantką] firmy [nazwa], która [czym się zajmuje]. Dzwonisz do osoby, która [skąd lead: zostawiła zgłoszenie / jest z listy klientów / porzuciła koszyk].
>
> CEL: [jeden cel, np. umówić 20-minutowe spotkanie online].
>
> PRZEBIEG:
> 1. Przywitaj się, przedstaw i zapytaj, czy to dobry moment.
> 2. Zadaj maksymalnie dwa krótkie pytania kwalifikujące: [pytanie 1], [pytanie 2].
> 3. Jeśli rozmówca jest zainteresowany — zaproponuj [następny krok] i potwierdź.
> 4. Domknij uprzejmie, zapowiedz [SMS/e-mail/oddzwonienie], podziękuj.
>
> TON: mów po polsku, krótko i naturalnie, maksymalnie 2 zdania na turę, nie naciskaj, nie przerywaj.
>
> KWALIFIKACJA: uznaj rozmówcę za zainteresowanego, gdy [warunek, np. potwierdzi chęć spotkania lub poda termin].
>
> OBIEKCJE:
> - „Nie mam czasu" → zaproponuj krótszą, dogodną porę.
> - „Za drogo" → podkreśl korzyść, zaproponuj rozmowę z ekspertem; nie podawaj cen spoza oferty.
> - „Skąd macie mój numer" → wyjaśnij spokojnie źródło zgłoszenia.
>
> GRANICE: nie obiecuj rzeczy spoza oferty, nie podawaj danych wrażliwych, nie zmyślaj cen ani terminów."

Dla rozmów **przychodzących** ten sam szkielet, ale bez „dzwonisz do…" (zamiast tego „odbierasz połączenie") i bez placeholderów.

### Dobre praktyki

- **Zawsze przetestuj** przed startem: „Testuj agenta" w przeglądarce (za darmo), a na koniec „Wyślij połączenie" na własny numer.
- Iteruj przez prawy panel „Asystent AI" — opisz zmianę słowami zamiast ręcznie przepisywać cały prompt.
- Trzymaj **jeden** główny cel na rozmowę — agent z jednym celem konwertuje lepiej niż „zrób wszystko".
- Do personalizacji outbound używaj placeholderów; sprawdź, że pole istnieje w źródle (plik 3).
- Nie pakuj całej wiedzy o produkcie do promptu — trzymaj to, co potrzebne do celu rozmowy. (Dedykowana baza wiedzy dla agenta jest „Wkrótce".)
- Po każdej większej zmianie promptu zrób szybki test głosowy — brzmienie „na uchu" bywa inne niż na papierze.

---

## 8. Najczęstsze problemy i pytania (FAQ)

**1. Agent nie dzwoni.**
Sprawdź kolejno: (a) kampania jest **Aktywna** (nie Zatrzymana) — Dashboard kampanii → „Uruchom kampanię"; (b) jest **przypisany numer** (ustawienia kampanii / zakładka numeru); (c) są **kredyty** (min. próg z sekcji 4); (d) jesteś w **oknie harmonogramu** (godziny + dni — plik 3); (e) źródło ma leady. Brak numeru lub niskie saldo blokują start (patrz dialogi w sekcji 4).

**2. Jak zmienić głos agenta?**
Zakładka **Agent** → sekcja **Głos** → **Zmień** → wybierz w modalu i **Zapisz głos**. Zapis jest natychmiastowy i synchronizuje agenta. Przed wyborem odsłuchaj próbki.

**3. Jak przetestować agenta za darmo?**
Zakładka **Agent** → **Testuj agenta** → wybierz „Agent dzwoni do klienta" lub „Klient dzwoni do agenta" → zezwól na mikrofon → **Rozpocznij rozmowę**. Rozmowa w przeglądarce **nie zużywa kredytów** i nie wymaga numeru ani weryfikacji.

**4. Czym różni się prompt wychodzący od przychodzącego?**
Wychodzący (outbound) = gdy agent sam dzwoni do leada; zna dane leada, więc może używać placeholderów `{{...}}`. Przychodzący (inbound) = gdy klient dzwoni do agenta; agent nie zna z góry rozmówcy, więc bez placeholderów. Oba edytujesz w „Zarządzaj promptem" (osobne zakładki).

**5. Jak sprawić, żeby agent umawiał spotkania?**
Dwa elementy: (a) podłącz **kalendarz** — Integracje → połącz kalendarz (np. Cal.com), potem zakładka Agent → **Narzędzia** → **Wybierz** kalendarz; (b) w promptcie napisz wprost cel: „umów spotkanie i potwierdź termin". Wtedy agent w trakcie rozmowy proponuje i rezerwuje termin.

**6. Ile trwa konfiguracja kampanii?**
Z kreatorem AI: kilka–kilkanaście minut. Odpowiadasz na pytania o firmę i ofertę, AI generuje prompty i pierwsze wypowiedzi, wybierasz głos, testujesz w przeglądarce i uruchamiasz. Źródło leadów i numer to kolejne kilka minut.

**7. Wygenerowany prompt mi nie pasuje — jak poprawić?**
Zakładka Agent → **Zarządzaj promptem** → w prawym panelu „Asystent AI" opisz zmianę po ludzku („skróć powitanie", „dodaj pytanie o budżet"). Możesz też edytować pola ręcznie. Na końcu **Zapisz i zsynchronizuj**. Zła iteracja? Użyj **„Cofnij do tutaj"**.

**8. Co to jest „Wyślij połączenie" i czy to kosztuje?**
To testowe połączenie **na żywo** na wskazany numer (przez numer kampanii) — prawdziwa rozmowa telefoniczna. Wymaga przypisanego numeru i zgody (checkbox). Do samego dopracowania promptu użyj darmowego „Testuj agenta" w przeglądarce.

**9. Nie mogę uruchomić kampanii — „Za mało kredytów".**
Doładuj saldo: przycisk **Doładuj kredyty** w dialogu prowadzi do `Ustawienia → Kredyty`. Próg to najtańsza operacja w Twoim scenariuszu (patrz plik 4 — cennik).

**10. Nie mogę uruchomić — „Przypisz numer telefonu".**
Kampania nie ma numeru. Kliknij **Przejdź do numeru**, przypisz numer w ustawieniach kampanii. Numer trzeba wcześniej kupić (wymaga zweryfikowanej firmy — plik 4).

**11. Jak zmienić typ kampanii (źródło leadów)?**
Nie da się zmienić po utworzeniu. Utwórz nową kampanię z właściwym typem. Agenta/prompt można odtworzyć szybko kreatorem.

**12. Kreator agenta nie pojawia się / chcę go wywołać ponownie.**
Kreator pokazuje się tylko dopóki prompt jest domyślny i nie został pominięty (stan zapamiętany per kampania). Jeśli chcesz zbudować prompt od zera, wejdź w **Zarządzaj promptem** → **Zacznij od nowa** (czyści czat) i przejdź wywiad w prawym panelu.

**13. Agent mówi w złym języku / zbyt formalnie / za długo.**
To kwestia promptu i pierwszej wypowiedzi. W „Zarządzaj promptem" doprecyzuj: „mów po polsku", „krótko i ciepło", „maksymalnie 2 zdania na turę". Domyślnie agent mówi po polsku, chyba że rozmówca wybierze inny język.

**14. Co to jest „Oddzwanianie" i kiedy włączyć?**
Przełącznik w zakładce Agent. Włącz, jeśli chcesz, by przy prośbie klienta o kontakt w innym terminie agent sam zaplanował oddzwonienie (klient poda godzinę). Dobre do kampanii, gdzie ludzie często proszą „proszę zadzwonić wieczorem".

**15. „Agent nie skonfigurowany" na ekranie testu.**
Znaczy, że dany kierunek (wychodzący/przychodzący) nie ma jeszcze zapisanego agenta. Wejdź w **Zarządzaj promptem**, uzupełnij prompt dla tego kierunku i **Zapisz i zsynchronizuj** — dopiero zapis tworzy agenta.

**16. Zapisałem prompt, ale zmiany „nie działają" w rozmowie.**
Upewnij się, że kliknąłeś **Zapisz i zsynchronizuj** (nie tylko wpisałeś tekst). Zapis synchronizuje agenta głosowego. Jeśli nadal źle — przetestuj ponownie („Testuj agenta") i sprawdź, czy edytujesz właściwą zakładkę (Przychodzące vs Wychodzące).

**17. Kalendarz nie pojawia się na liście w „Narzędzia".**
Najpierw połącz kalendarz na koncie: Integracje → połącz (np. Cal.com). Potem w zakładce Agent → Narzędzia → **Wybierz** pojawi się na liście (plik 4).

**18. Jak dobrać głos do kampanii?**
Odsłuchaj kilka próbek w modalu „Wybierz głos agenta". Dopasuj do odbiorcy: ciepły/spokojny do klienta indywidualnego, rzeczowy do B2B. To subiektywne — najlepiej przetestować w rozmowie.

---

## Obiekcje sprzedażowe (gotowe odpowiedzi)

- **„To pewnie brzmi jak robot."** → „Głos i styl dobiera się samodzielnie — odsłuchaj próbki w panelu i przetestuj rozmowę w przeglądarce za darmo. Większość osób nie rozpoznaje, że to AI. Sam ocenisz, zanim wydasz złotówkę."
- **„Konfiguracja będzie skomplikowana."** → „Jest kreator: odpowiadasz na kilka pytań o firmę, a AI pisze gotowe prompty i pierwsze wypowiedzi. Start to kilkanaście minut, a asystent w panelu i ekspert (bezpłatne spotkanie) pomogą w razie potrzeby."
- **„Nie chcę płacić, zanim sprawdzę."** → „Konfiguracja i test w przeglądarce nie kosztują nic i nie wymagają weryfikacji ani numeru. Płacisz dopiero za realne, odebrane rozmowy."
- **„Mam leady w innym systemie / z reklam FB."** → „Podłączasz je przez HTTP Webhook (Make.com/Zapier/własny backend) — leady wpadają automatycznie i agent dzwoni od razu. Integracja Meta Forms jest w przygotowaniu."
- **„Czy agent umówi spotkanie?"** → „Tak — podpinasz kalendarz w Narzędziach, a w promptcie ustawiasz cel „umów spotkanie". Agent proponuje i rezerwuje termin w trakcie rozmowy."
- **„Boję się o zgodność z prawem."** → „Przed uruchomieniem potwierdzasz podstawę prawną kontaktu (jednorazowo na kampanię), a firma przechodzi weryfikację (KYB). Dbamy o to, żeby dzwonić zgodnie z zasadami."

---

## Skróty ścieżek (ściąga dla supportu)

- Utworzyć kampanię: **Nowa kampania** → typ → **Dalej** → nazwa → **Utwórz kampanię**.
- Zmienić głos: Kampania → **Agent** → Głos → **Zmień** → **Zapisz głos**.
- Edytować prompt: Kampania → **Agent** → **Zarządzaj promptem** → zakładka Przychodzące/Wychodzące → **Zapisz i zsynchronizuj**.
- Test za darmo: Kampania → **Agent** → **Testuj agenta**.
- Test na żywo: Kampania → **Agent** → **Wyślij połączenie** (wymaga numeru + zgody).
- Uruchomić: Kampania → **Dashboard** → **Uruchom kampanię** (numer + kredyty + oświadczenie).
- Zatrzymać: Kampania → **Dashboard** → **Zatrzymaj kampanię** (anuluje zaplanowane akcje).
- Doładować kredyty: dialog „Za mało kredytów" → **Doładuj kredyty** lub `Ustawienia → Kredyty`.
