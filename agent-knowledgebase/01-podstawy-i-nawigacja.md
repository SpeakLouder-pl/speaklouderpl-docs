# SpeakLouder — KB dla agenta AI (1/4): Podstawy i nawigacja

> **Wewnętrzna baza wiedzy dla asystenta AI SpeakLouder.** Ten plik NIE jest publikowany na stronie dokumentacji — to materiał referencyjny dla asystenta (support + sprzedaż), który ma znać odpowiedź na wszystko: co to jest, gdzie się co ustawia, jak, ile kosztuje i jak to sprzedać. Panel aplikacji: `https://app.speaklouder.pl`. Dokumentacja publiczna: `https://docs.speaklouder.ai`. Umówienie eksperta: `https://cal.com/speaklouder/30min`. **Język odpowiedzi do użytkownika: zawsze polski.**
>
> Ten plik to część 1 z 4. Pozostałe: **02** (Kampanie i Agent), **03** (Workflow, Leady, Aktywność), **04** (Numery, Integracje, Kredyty, Konto). Gdy pytanie wykracza poza „podstawy i nawigację", odsyłaj do właściwego pliku.

---

## 1. Czym jest SpeakLouder

### Definicja w jednym zdaniu
SpeakLouder to platforma z **agentem głosowym AI**, który dzwoni do leadów (i odbiera połączenia przychodzące) zamiast zespołu handlowego — prowadzi naturalną rozmowę telefoniczną, kwalifikuje kontakt, a po rozmowie automatycznie wykonuje działania (SMS, e-mail, transfer do człowieka, zapis w CRM).

### Co robi agent, krok po kroku
1. **Dzwoni** do leada ustawionym głosem, według instrukcji (promptu) przygotowanych osobno dla rozmów wychodzących i przychodzących.
2. **Prowadzi rozmowę** — wita się, zadaje pytania, odpowiada na pytania klienta, realizuje cel (np. umówienie demo, potwierdzenie zainteresowania, odzyskanie porzuconego koszyka).
3. **Kwalifikuje** — ocenia, czy lead jest zainteresowany (ocena `Zainteresowanie leada` 0–100 lub własny warunek zdefiniowany przez klienta).
4. **Działa po rozmowie** — może wysłać SMS lub e-mail follow-up, przekazać rozmowę na żywo do handlowca (transfer), zaplanować oddzwonienie albo wysłać dane do zewnętrznego systemu (webhook).
5. **Zapisuje wszystko** — nagranie, transkrypcję (dymki agent/klient), podsumowanie AI, wynik i status leada trafiają do wbudowanego, prostego CRM.

### Dla kogo (ICP — idealny klient)
- **Firmy z dużą liczbą leadów przychodzących**, których handlowcy nie nadążają obdzwonić na czas (agencje nieruchomości, ubezpieczenia, fotowoltaika, edukacja, kliniki, e-commerce, B2B SaaS).
- **Sklepy internetowe** (zwłaszcza Shopify) walczące z porzuconymi koszykami.
- **Zespoły sprzedaży** chcące kwalifikować leady 24/7, bez zatrudniania i szkolenia kolejnych osób na infolinii.
- **Firmy z bazami CSV** (stare kontakty, listy do reaktywacji), które chcą je szybko przetworzyć.
- **Marketerzy performance** kupujący leady z reklam (Meta/Google), gdzie liczy się czas kontaktu (im szybciej zadzwonisz, tym większa konwersja).

### Typowe scenariusze zastosowania
| Scenariusz | Jak działa SpeakLouder |
|---|---|
| **Leady z reklam** | Formularz/reklama → webhook → agent dzwoni w kilka sekund, kwalifikuje, umawia demo lub przekazuje do handlowca. |
| **Porzucone koszyki** | Integracja Shopify → agent dzwoni do klienta, który nie dokończył zakupu, i pomaga sfinalizować. |
| **Bazy CSV** | Import listy kontaktów → agent obdzwania całą bazę wg harmonogramu. |
| **Reaktywacja** | Stara baza klientów → kampania odzyskująca, oferta powrotu. |
| **Infolinia przychodząca** | Agent odbiera połączenia (inbound) i obsługuje pytania / kwalifikuje / umawia. |

### Wartość, jaką daje (dla klienta)
- **Oszczędność czasu handlowców** — AI robi żmudne pierwsze telefony i kwalifikację; ludzie zajmują się tylko gorącymi leadami.
- **Natychmiastowy kontakt** — agent dzwoni od razu po pojawieniu się leada, o każdej porze objętej harmonogramem (nie czeka do jutra rana).
- **Kwalifikacja 24/7** — brak przerw, urlopów, zmęczenia; skalowanie bez rekrutacji.
- **Pełna dokumentacja** — każda rozmowa nagrana, przepisana i podsumowana; nic nie ginie.
- **Przewidywalny koszt** — płacisz kredytami za faktycznie odebrane rozmowy, nie za etaty.

---

## SEKCJA SPRZEDAŻOWA — propozycja wartości i obiekcje

### Główna propozycja wartości (elevator pitch)
„SpeakLouder to Twój handlowiec-AI, który dzwoni do każdego leada w kilka sekund, kwalifikuje go w naturalnej rozmowie i przekazuje Ci tylko tych gotowych do zakupu — 24 godziny na dobę, bez rekrutacji i bez etatów."

### Główne korzyści (do użycia w rozmowie sprzedażowej)
- **Szybkość reakcji** — kontakt z leadem w sekundy, nie w godziny. To najsilniejszy czynnik konwersji przy leadach z reklam.
- **Skalowalność** — jeden agent obsłuży 10 albo 10 000 leadów; koszt rośnie liniowo z liczbą rozmów, nie skokowo z zatrudnieniem.
- **Spójność** — agent zawsze mówi to, co ustalono, nie ma gorszych dni, trzyma się skryptu i celu.
- **Mierzalność** — każdy telefon ma transkrypcję, wynik i ocenę zainteresowania; łatwo optymalizować.
- **Niskie ryzyko wejścia** — konfiguracja i test agenta w przeglądarce są darmowe; płacisz dopiero, gdy agent realnie dzwoni.

### Przykładowe ROI (do zilustrowania)
- Handlowiec obdzwania ~40–60 leadów dziennie. Agent AI może dzwonić równolegle do wielu naraz, bez limitu godzin.
- Odebrana rozmowa kosztuje **6 kredytów** (≈ 6 PLN netto przy proporcji ~1 kredyt ≈ 1 PLN, patrz plik 04). Nieodebrane rozmowy i poczta głosowa są **bezpłatne**.
- Przy koszcie kilku złotych za rozmowę i kwalifikacji dziesiątek leadów dziennie, koszt jednego zakwalifikowanego leada bywa niższy niż godzina pracy handlowca. Dokładne stawki i doładowania → **plik 04**.

### Jak odpowiadać na „po co mi to / czym się różni od zwykłego call center"
- **„Mam już handlowców."** → SpeakLouder ich nie zastępuje, tylko odciąża: robi pierwszy kontakt i kwalifikację, a handlowcy dostają wyłącznie gotowe leady. Więcej domkniętych transakcji przy tym samym zespole.
- **„To to samo co call center."** → Call center to koszt stały, grafik, rotacja, szkolenia i zmienna jakość. Agent AI dzwoni natychmiast, 24/7, zawsze wg skryptu, z pełną transkrypcją i oceną każdej rozmowy, a koszt jest za faktyczne rozmowy.
- **„Czy klient pozna, że to AI?"** → Głos jest naturalny (można odsłuchać próbki), a rozmowa płynna. Zawsze rekomendujemy przetestować agenta w przeglądarce przed startem — test jest darmowy.
- **„Czy to legalne / a RODO?"** → Platforma prowadzi weryfikację firmy (KYB) i wymaga akceptacji regulaminu, polityki prywatności, DPA oraz zgód AI Act przed dzwonieniem do prawdziwych leadów. Szczegóły → plik 04 i sekcja „Bezpieczeństwo" niżej.
- **„Ile to kosztuje na start?"** → Konfiguracja i testy są darmowe. Płacisz kredytami dopiero za realne rozmowy i abonament numeru. Można zacząć od małego doładowania.
- Zawsze, gdy klient chce wdrożenia „pod siebie", proponuj **bezpłatne spotkanie z ekspertem** (`cal.com/speaklouder/30min`).

---

## 2. Słownik pojęć

- **Konto (organizacja)** — jedno konto użytkownika = jedna organizacja. Współdzieli **kredyty**, **numery telefonów** i **integracje** między wszystkimi kampaniami. Wszystkie kampanie „żyją" wewnątrz jednego konta.
- **Kampania** — jedna grupa leadów z własną, odrębną konfiguracją: typ (źródło leadów), agent, workflow, przypisany numer, ustawienia. Codzienna praca odbywa się „wewnątrz kampanii". Kampania jest **Aktywna** (agent dzwoni) albo **Wstrzymana** (nie dzwoni).
- **Lead** — pojedynczy kontakt (osoba) w danej kampanii. Ma dane (imię, e-mail, telefon, pola własne), status, historię akcji i ocenę zainteresowania.
- **Agent** — konfiguracja **głosu + promptu**, czyli sposób, w jaki AI rozmawia w danej kampanii. Ustawiany osobno dla każdej kampanii. Szczegóły → plik 02.
- **Głos** — barwa/charakter mówcy agenta (np. Marek, Tomek, Ania). Wybiera się z gotowych próbek; można odsłuchać przed zapisaniem.
- **Prompt** — instrukcje tekstowe dla agenta: kim jest, co ma osiągnąć, jak reagować. Osobny dla rozmów **wychodzących** i **przychodzących**. Może być wygenerowany przez kreator AI lub napisany ręcznie.
- **Workflow (przepływ pracy) / sekwencja / harmonogram** — scenariusz kampanii: jaka jest kolejność kroków (call, SMS, e-mail), z jakimi opóźnieniami, w jakich godzinach i dniach agent dzwoni oraz co dzieje się automatycznie po rozmowie. Szczegóły → plik 03.
- **Kwalifikacja** — proces oceny, czy lead jest wartościowy/zainteresowany. Domyślnie robi to AI; można podać **własny warunek zakwalifikowania** własnymi słowami.
- **Zainteresowanie leada** — ocena AI w skali **0–100**, wyliczana z treści rozmów i aktualizowana po każdym połączeniu. Nie jest polem do ręcznego wpisywania.
- **Kredyty** — wewnętrzna waluta całego konta. Płaci się nimi za odebrane rozmowy, SMS-y i abonament numerów. Doładowanie jednorazowe (nie subskrypcja). Szczegóły → plik 04.
- **Numer telefonu** — numer, z którego agent dzwoni. Należy do konta, obsługuje w danym momencie tylko jedną kampanię, ma stały abonament miesięczny. Szczegóły → plik 04.
- **Integracja** — połączenie SpeakLouder z narzędziem zewnętrznym (Make.com, Shopify, Gmail, kalendarz Cal.com). Konfigurowana na poziomie konta lub kampanii. Szczegóły → plik 04.
- **Webhook** — automatyczna wymiana danych przez HTTP POST: leady mogą wpadać do kampanii webhookiem (źródło), a dane po rozmowie mogą być wysyłane webhookiem do zewnętrznego systemu.
- **Token** — sekretny klucz w adresie webhooka źródła leadów, identyfikujący kampanię. Traktować jak hasło — nie ujawniać publicznie (w komunikacji token w URL zawsze maskujemy/blurujemy).
- **Weryfikacja / KYB** — weryfikacja firmy (Know Your Business) przez dostawcę **Didit**. Wymagana do dzwonienia do prawdziwych leadów i kupna numerów. Szczegóły → plik 04.
- **Poczta wychodząca** — podłączony Gmail, z którego agent wysyła e-maile follow-up po rozmowie.
- **Transfer do handlowca** — przekazanie trwającego połączenia na żywo do człowieka (np. gdy lead jest gorący).
- **Oddzwanianie (callback)** — funkcja, w której agent sam planuje i wykonuje ponowne połączenie, gdy klient poprosi o kontakt w konkretnym terminie.

---

## 3. Rejestracja i logowanie

### Ekrany publiczne (dostępne bez logowania)
| Ścieżka | Ekran |
|---|---|
| `/login` | Logowanie (e-mail + hasło lub Google) |
| `/register` | Rejestracja nowego konta |
| `/forgot-password` | Prośba o link do resetu hasła |
| `/reset-password` | Ustawienie nowego hasła (po kliknięciu w link z maila) |
| `/auth/callback` | Ekran pośredni po powrocie z logowania Google / potwierdzenia e-maila |
| `/legal/:doc` | Dokumenty prawne (regulamin, polityka, DPA) |
| `/mfa-challenge` | Weryfikacja dwuetapowa (jeśli konto ma włączone 2FA) |

### Logowanie
- **E-mail + hasło** — na `/login`. Wymaga podania e-maila i hasła; przy błędzie pojawia się komunikat „Logowanie nieudane".
- **Google SSO** — przycisk „Zaloguj się z Google" (logowanie jednym kliknięciem przez konto Google, bez osobnego hasła).
- Po zalogowaniu ścieżka `/` przekierowuje do `/dashboard`.
- Logując się, użytkownik akceptuje **regulamin** (`/legal/terms`) i **politykę prywatności** (`/legal/privacy`).

### Rejestracja (`/register`)
- Pola: **Imię i nazwisko**, **E-mail**, **Hasło** (minimum **8 znaków**). Lub rejestracja przez Google.
- Po założeniu konta system może od razu zalogować (jeśli jest sesja) albo wyświetlić ekran **„Sprawdź skrzynkę"** — trzeba kliknąć link aktywacyjny wysłany na e-mail.
- Rejestrując się, użytkownik akceptuje regulamin i politykę prywatności.

### Reset hasła
- **`/forgot-password`** — użytkownik podaje e-mail, dostaje link do resetu.
- **`/reset-password`** — po kliknięciu w link ustawia nowe hasło.
- Alternatywnie: w **Ustawieniach → Konto** jest przycisk „Wyślij link", który wysyła link resetu na e-mail konta (patrz plik 04).

### MFA / 2FA (uwierzytelnianie dwuetapowe)
- SpeakLouder wspiera **weryfikację dwuetapową kodem TOTP** (aplikacja typu Google Authenticator / Authy) — poziom bezpieczeństwa **AAL2**.
- Jeśli konto ma zweryfikowany czynnik 2FA, po zalogowaniu pojawia się ekran **`/mfa-challenge`**: należy wpisać **6-cyfrowy kod** z aplikacji uwierzytelniającej.
- Jeśli 2FA nie jest skonfigurowane, ekran pomija się automatycznie i użytkownik trafia od razu do panelu.
- Komunikaty pomocnicze: „Weryfikacja 2FA wyłączona" / „Nie udało się rozpocząć 2FA" → w takim wypadku wyloguj się i spróbuj ponownie; jeśli problem się powtarza, skontaktuj się z supportem.

### Dokumenty prawne (`/legal/:doc`)
Renderowane w aplikacji pod następującymi slugami:
- `/legal/terms` oraz `/legal/regulamin` → **Regulamin**
- `/legal/privacy` → **Polityka Prywatności**
- `/legal/dpa` → **Umowa Powierzenia Przetwarzania Danych (DPA)**

Nieznany slug pokazuje „Nie znaleziono dokumentu". Dokumenty prawne akceptuje się także w procesie weryfikacji firmy (plik 04).

---

## 4. Globalna nawigacja (menu konta, po lewej — poza kampanią)

Górna część paska bocznego:
- **Logo SpeakLouder** (u samej góry) — klik prowadzi do `/dashboard`.
- **Przycisk „Nowa kampania"** (niebieski, pod logo) — otwiera kreator tworzenia kampanii (`/dashboard/campaigns?new=1`). Widoczny tylko poza kontekstem kampanii.

Menu główne:
| Pozycja | Dokąd prowadzi | Co robi |
|---|---|---|
| **Pierwsze kroki** | `/dashboard/get-started` | Globalny onboarding konta (powitanie, film, pomoc). |
| **Dashboard** | `/dashboard` | Przegląd wszystkich kampanii (KPI, wykres, ostatnie kampanie). |
| **Kampanie** | `/dashboard/campaigns` | Lista wszystkich kampanii. |
| **Baza wiedzy** | `/dashboard/knowledgebase` | Oznaczona **„Wkrótce"** — nieaktywna, funkcja w przygotowaniu. |
| **Numery telefonów** | `/dashboard/phone-numbers` | Rozwija: **Moje numery** i **Kup numer**. |
| **Integracje** | `/dashboard/integrations` | Połączenia z narzędziami zewnętrznymi. |

Sekcja **„Konto"** (na dole):
- **Promo „Umów spotkanie z ekspertem"** — kafelek z linkiem do `cal.com/speaklouder/30min` („Bezpłatnie pomożemy skonfigurować kampanię i agenta"). Chowa się, gdy rozwinięte są „Ustawienia".
- **Ustawienia** (`/dashboard/settings`) — rozwija zakładki: **Konto**, **Agencja**, **Tagi**, **Weryfikacja**, **Kredyty** (billing), **Cennik**.
- **Pomoc** — link do dokumentacji (`docs.speaklouder.ai`, otwiera się w nowej karcie) i jednocześnie otwiera panel asystenta AI.

Na samym dole paska (stopka): **karta użytkownika** (avatar + imię + e-mail). Klik otwiera menu: **Konto** (→ Ustawienia), **Billing** (→ `settings?tab=billing`), **Wyloguj się**.

---

## 5. Nawigacja wewnątrz kampanii + przełącznik kampanii

Po wejściu do dowolnej kampanii (`/dashboard/campaigns/:id/...`) pasek boczny zmienia się na zakładki tej kampanii. Zamiast przycisku „Nowa kampania" u góry pojawia się **przełącznik kampanii** — rozwijana lista, w której szybko zmienisz kampanię (wybór przenosi na dashboard nowej kampanii; nie zachowuje bieżącej zakładki).

Zakładki kampanii (kolejność w menu):
| Zakładka | Ścieżka | Opis (szczegóły w pliku) |
|---|---|---|
| **Pierwsze kroki** | `/campaigns/:id/get-started` | Checklista uruchomienia kampanii (plik 02). |
| **Dashboard** | `/campaigns/:id/dashboard` | KPI kampanii, wykres, ostatnia aktywność (plik 02). |
| **Leady** | `/campaigns/:id/leads` | CRM — lista leadów (plik 03). |
| **Źródło** | `/campaigns/:id/source` | Konfiguracja źródła leadów (plik 03). |
| **Workflow** | `/campaigns/:id/workflow` | Sekwencja, harmonogram, automatyzacje (plik 03). |
| **Agent** | `/campaigns/:id/agent` | Głos i prompt agenta (plik 02). |
| **Numer telefonu** | `/campaigns/:id/phone` | Przypisanie numeru (plik 04). |
| **Aktywność** | `/campaigns/:id/activity/calls` | Rozwija: **Połączenia** i **Dziennik akcji** (plik 03). |

Na dole menu kampanii:
- **Ustawienia kampanii** (`/campaigns/:id/settings`).
- **Pomoc** — dokumentacja + otwarcie asystenta AI.
- Karta użytkownika (jak wyżej).

---

## 6. Górny pasek (na każdej stronie panelu)

Po prawej stronie górnego paska (nagłówka) znajdują się:
- **Licznik kredytów** (ikona monety + liczba) — aktualne saldo konta. Klik prowadzi do `/dashboard/settings?tab=billing` (zakładka Kredyty).
- **Ikona ✨ Asystent AI** — otwiera/zamyka panel asystenta AI. Asystent **pomaga we wszystkim** (konfiguracja kampanii/agenta, analiza leadów, strategia kontaktu, nawigacja, pytania o produkt) i jest **dostępny z każdego ekranu**. To główny kanał samoobsługowej pomocy w panelu.
- **Ikona motywu** (słońce/księżyc) — przełącza wygląd **jasny/ciemny**.

> Uwaga: ikona powiadomień (dzwonek) jest w kodzie ukryta — nie ma jeszcze systemu powiadomień. Nie obiecuj klientowi powiadomień w panelu.

---

## 7. Pełna mapa routingu (wszystkie URL-e)

### Poziom konta
| Ścieżka | Strona |
|---|---|
| `/` | Przekierowanie → `/dashboard`. |
| `/login`, `/register`, `/forgot-password`, `/reset-password` | Ekrany autoryzacji. |
| `/auth/callback` | Powrót z logowania zewnętrznego / potwierdzenia e-maila. |
| `/mfa-challenge` | Weryfikacja 2FA (jeśli włączona). |
| `/legal/:doc` | Dokumenty prawne (`terms`/`regulamin`, `privacy`, `dpa`). |
| `/dashboard` | **Przegląd** — podsumowanie wszystkich kampanii. |
| `/dashboard/get-started` | **Pierwsze kroki** konta (onboarding). |
| `/dashboard/analytics` | **Analityka** (KPI + wykresy). |
| `/dashboard/campaigns` | **Lista kampanii** (`?new=1` otwiera kreator nowej). |
| `/dashboard/integrations` | **Integracje**. |
| `/dashboard/knowledgebase` | **Baza wiedzy** — „Wkrótce". |
| `/dashboard/phone-numbers` | **Moje numery**. |
| `/dashboard/phone-numbers/buy` | **Kup numer**. |
| `/dashboard/settings` | **Ustawienia**; zakładki przez `?tab=`: (brak/`konto`), `agencja`, `tagi`, `weryfikacja`, `billing` (Kredyty), `cennik`. |

### Poziom kampanii (`:id` = identyfikator kampanii)
| Ścieżka | Strona |
|---|---|
| `/dashboard/campaigns/:id` | Przekierowanie → `get-started`. |
| `/dashboard/campaigns/:id/get-started` | Checklista pierwszych kroków kampanii. |
| `/dashboard/campaigns/:id/dashboard` | Dashboard kampanii (KPI, wykres, ostatnia aktywność). |
| `/dashboard/campaigns/:id/agent` | Konfiguracja agenta (głos + prompt). |
| `/dashboard/campaigns/:id/agent/knowledgebase` | Baza wiedzy agenta — „Wkrótce". |
| `/dashboard/campaigns/:id/workflow` | Przepływ pracy (sekwencja, harmonogram, automatyzacje). |
| `/dashboard/campaigns/:id/source` | Źródło leadów. |
| `/dashboard/campaigns/:id/leads` | CRM — lista leadów. |
| `/dashboard/campaigns/:id/leads/:leadId` | Karta pojedynczego leada. |
| `/dashboard/campaigns/:id/activity` | Przekierowanie → `activity/calls`. |
| `/dashboard/campaigns/:id/activity/calls` | Połączenia (z transkrypcją i podsumowaniem). |
| `/dashboard/campaigns/:id/activity/action-log` | Dziennik akcji. |
| `/dashboard/campaigns/:id/phone` | Numer telefonu kampanii. |
| `/dashboard/campaigns/:id/settings` | Ustawienia kampanii. |

**Nieznane ścieżki** przekierowują do `/dashboard`.

---

## 8. Strona Przegląd (`/dashboard`) i Analityka (`/dashboard/analytics`)

### Przegląd (`/dashboard`) — tytuł „Przegląd"
Ogólny widok całego konta:
- **Cztery karty KPI:** „Łącznie połączeń" (we wszystkich kampaniach), „Aktywne kampanie" (z liczbą wstrzymanych pod spodem), „Zakwalifikowanych leadów" (z liczby wszystkich leadów), „Łączne leady".
- **Wykres aktywności** (interaktywny) — trend w czasie.
- **Tabela „Ostatnie kampanie"** — skrót najnowszych kampanii z szybkim wejściem.

To pierwszy ekran po zalogowaniu — służy do szybkiej oceny „jak idzie" na poziomie całego konta.

### Analityka (`/dashboard/analytics`) — tytuł „Analityka"
Pogłębione statystyki:
- **Cztery karty KPI:** „Wszystkie leady" (z liczby różnych źródeł), „Zakwalifikowanych" (+ wskaźnik kwalifikacji w %), „Połączeń łącznie" (+ liczba SMS), „Aktywne kampanie" (z łącznej liczby kampanii).
- **Wykres „Statusy leadów"** (kołowy) — rozkład leadów: Nowy, W toku, Zakwalifikowany, Niezakwalifikowany, Bez kontaktu.
- **Wykres „Statusy kampanii"** (kołowy) — Aktywna vs Wstrzymana.
- **Wykres „Źródła leadów"** (słupkowy) — skąd pochodzą leady.
- **Wykres „Aktywność per lead"** (słupkowy) — połączenia i SMS-y dla poszczególnych leadów.

Różnica: **Przegląd** = szybki puls konta; **Analityka** = rozbicia i rozkłady do analizy skuteczności.

---

## 9. Onboarding konta (`/dashboard/get-started`)

Ekran „Pierwsze kroki" na poziomie konta (osobny od checklisty wewnątrz kampanii):
- **Powitanie** z imieniem użytkownika.
- **Krok „Utwórz pierwszą kampanię"** — kafelek prowadzący do istniejącej pierwszej kampanii albo (jeśli brak) do kreatora nowej kampanii.
- **Film instruktażowy** — osadzone wideo z YouTube (krótki przewodnik po konfiguracji agenta).
- **Sekcja „Potrzebujesz pomocy?"** z trzema kartami:
  - **Porozmawiaj z asystentem** — otwiera panel asystenta AI.
  - **Umów spotkanie z ekspertem** — link do `cal.com/speaklouder/30min` (bezpłatna pomoc we wdrożeniu).
  - **Otwórz dokumentację** — link do `docs.speaklouder.ai`.

Ten ekran to najlepszy punkt startu dla nowego użytkownika. Onboarding wewnątrz konkretnej kampanii (checklista 6–7 kroków) opisano w pliku 02.

---

## 10. Jak asystent AI powinien pomagać

### Ton i zasady
- **Zawsze po polsku**, rzeczowo, krótko i konkretnie. Bez lania wody i bez emoji.
- **Najpierw ustal kontekst** — zanim doradzisz, dopytaj o to, co niezbędne: jakiego typu jest kampania (webhook/Shopify/CSV/Meta), na jakim jest etapie (skonfigurowana? uruchomiona?), czy firma jest zweryfikowana (KYB), czy ma przypisany numer i kredyty. Bez tego łatwo o błędną poradę.
- **Podawaj dokładne ścieżki** (np. „Ustawienia → Weryfikacja", `/dashboard/settings?tab=weryfikacja`) i konkretne nazwy przycisków — nie ogólniki.
- **Nie ujawniaj tokenów/sekretów** — w komunikacji token webhooka zawsze maskuj.
- **Nie obiecuj funkcji oznaczonych „Wkrótce"** (Baza wiedzy, Baza wiedzy agenta, Meta Forms, Meta Ads, Zapier) — mów wprost, że są w przygotowaniu.
- **Nie ujawniaj wewnętrznych szczegółów technicznych** (nazwy edge functions, kody statusów Supabase, surowe skip-reasony). Klientowi tłumacz je czytelnym językiem (mapowanie w pliku 03).

### Kiedy kierować do dokumentacji, a kiedy do eksperta
- **Do dokumentacji** (`docs.speaklouder.ai`) — gdy klient chce samodzielnie przejść procedurę krok po kroku, którą da się opisać (konfiguracja, import CSV, integracja Make).
- **Do eksperta** (`cal.com/speaklouder/30min`) — gdy klient chce, żeby ktoś skonfigurował kampanię/agenta „pod niego", ma złożony przypadek wdrożeniowy, negocjuje warunki, albo waha się przed zakupem (kwalifikacja sprzedażowa).
- **Do supportu** — przy błędach z kodem (np. „Błąd E1001. Skontaktuj się z supportem"), problemach z płatnościami, weryfikacją KYB lub podejrzeniu awarii.

### Kody błędów (do supportu — skrót)
Jeśli klient zgłasza komunikat z kodem, to błąd „do supportu" (nieoczekiwany/serwerowy):
- **E1001** — nie udało się wywołać funkcji (błąd sieci/relay).
- **E1003** — błąd HTTP bez czytelnego pola błędu.
- **E1203** — ogólny błąd serwera/bazy.
- **E1204** — przekroczono limit zapytań / przeciążenie.
Komunikaty **bez kodu** (np. „Zaloguj się ponownie", „Nie znaleziono kampanii", „Przypisz najpierw numer") to działania, które klient może naprawić sam — poinstruuj go, co zrobić.

### FAQ — pytania i gotowe odpowiedzi (zakres: podstawy i nawigacja)

**1. Czym właściwie jest SpeakLouder?**
To platforma z agentem głosowym AI, który dzwoni do Twoich leadów (i odbiera połączenia), prowadzi rozmowę, kwalifikuje kontakt i po rozmowie wykonuje działania (SMS, e-mail, transfer, zapis w CRM). Zastępuje pierwszy, powtarzalny kontakt telefoniczny.

**2. Czym różni się od zwykłego call center?**
Dzwoni natychmiast i 24/7, zawsze wg ustalonego skryptu, z pełną transkrypcją i oceną każdej rozmowy, a koszt jest za faktyczne rozmowy — bez etatów, grafików i rotacji.

**3. Ile to kosztuje na start?**
Konfiguracja i test agenta w przeglądarce są darmowe. Płacisz kredytami dopiero za realnie odebrane rozmowy (6 kredytów), opcjonalne SMS-y (0,4) i abonament numeru. Nieodebrane rozmowy i e-maile są darmowe. Szczegóły cennika → dopytaj lub zajrzyj do Ustawienia → Cennik.

**4. Gdzie się loguję?**
Na `https://app.speaklouder.pl/login` — e-mailem i hasłem albo przez Google. Nie pamiętasz hasła? Kliknij „Nie pamiętasz?" i zresetuj przez e-mail.

**5. Jak założyć konto?**
Na `/register`: podaj imię i nazwisko, e-mail i hasło (min. 8 znaków) albo zarejestruj się przez Google. Może być wymagane potwierdzenie e-maila linkiem aktywacyjnym.

**6. Jak zresetować hasło?**
Na ekranie logowania kliknij „Nie pamiętasz?" (`/forgot-password`), podaj e-mail i kliknij link, który przyjdzie na skrzynkę (`/reset-password`). Można też wysłać link z Ustawienia → Konto.

**7. Co to jest ten ekran z kodem po zalogowaniu?**
To weryfikacja dwuetapowa (2FA). Jeśli masz ją włączoną, wpisz 6-cyfrowy kod z aplikacji uwierzytelniającej. Jeśli jej nie ustawiałeś, ten ekran się nie pojawia.

**8. Gdzie znajdę moje kampanie?**
W menu po lewej: „Kampanie" (`/dashboard/campaigns`). Aby wejść do konkretnej, kliknij „Szczegóły". Wewnątrz kampanii możesz przełączać się między nimi rozwijaną listą u góry menu.

**9. Jak utworzyć nową kampanię?**
Kliknij „Nowa kampania" (przycisk u góry menu), wybierz typ (źródło leadów), nadaj nazwę i utwórz. Trafisz na checklistę „Pierwsze kroki". Szczegóły → plik 02.

**10. Gdzie ustawię głos i to, co mówi agent?**
Wewnątrz kampanii: zakładka „Agent". Tam wybierzesz głos i prompt (osobny dla rozmów wychodzących i przychodzących). Szczegóły → plik 02.

**11. Gdzie sprawdzę saldo kredytów?**
W górnym pasku (licznik z ikoną monety) albo w Ustawienia → Kredyty (`/dashboard/settings?tab=billing`). Doładowanie → tam samo (plik 04).

**12. Gdzie zobaczę nagrania i transkrypcje rozmów?**
Wewnątrz kampanii: Aktywność → Połączenia (`/campaigns/:id/activity/calls`). Znajdziesz tam kierunek rozmowy, wynik, długość, podsumowanie AI i pełną transkrypcję (plik 03).

**13. Gdzie są ustawienia konta?**
Menu → „Ustawienia" (`/dashboard/settings`). Zakładki: Konto, Agencja, Tagi, Weryfikacja, Kredyty, Cennik (plik 04).

**14. Jak zmienić motyw na ciemny/jasny?**
Ikoną słońca/księżyca w górnym pasku (lub w Ustawienia → Konto → Preferencje).

**15. Co to jest ikona ✨ w rogu?**
To asystent AI — pomaga we wszystkim wewnątrz panelu (konfiguracja, analiza, nawigacja, pytania o produkt). Jest dostępny z każdego ekranu.

**16. Czy moje dane są bezpieczne / a RODO?**
Tak — platforma wymaga akceptacji regulaminu, polityki prywatności i umowy powierzenia danych (DPA), a przed dzwonieniem do prawdziwych leadów przechodzi się weryfikację firmy (KYB) oraz zgody, w tym zgodę AI Act. Dostęp do konta dla supportu jest opcjonalny (przełącznik w Ustawieniach). Wspieramy też logowanie dwuetapowe (2FA). Szczegóły prawne w dokumentach `/legal/*` i w pliku 04.

**17. Gdzie znajdę regulamin / politykę prywatności / DPA?**
Pod adresami `/legal/terms`, `/legal/privacy`, `/legal/dpa`. Linki są też przy logowaniu, rejestracji i w procesie weryfikacji.

**18. Czy mogę tylko przetestować, zanim zapłacę?**
Tak. Konfiguracja i rozmowa testowa w przeglądarce („Testuj agenta") są darmowe i nie zużywają kredytów, a firma nie musi być jeszcze zweryfikowana. Płacisz dopiero, gdy agent realnie dzwoni.

**19. Dlaczego niektóre pozycje mają etykietę „Wkrótce"?**
To funkcje w przygotowaniu (Baza wiedzy konta, Baza wiedzy agenta, Meta Forms, Meta Ads, Zapier). Są widoczne, ale nieaktywne. Powiadomimy, gdy będą gotowe.

**20. Nie widzę powiadomień w panelu — gdzie one są?**
System powiadomień w panelu nie jest jeszcze dostępny. O najważniejszych zdarzeniach informujemy w karcie leada, dzienniku akcji i (opcjonalnie) e-mailem/webhookiem.

**21. Czym różni się „Przegląd" od „Analityki"?**
„Przegląd" (`/dashboard`) to szybki puls całego konta. „Analityka" (`/dashboard/analytics`) to rozbicia i wykresy (statusy leadów, źródła, aktywność) do głębszej analizy skuteczności.

**22. Jak przełączyć się między kampaniami?**
Wewnątrz kampanii, u góry menu po lewej, jest rozwijana lista — wybierz inną kampanię. Wybór przenosi na jej dashboard.

**23. Gdzie umówię pomoc z człowiekiem?**
Kliknij „Umów spotkanie z ekspertem" (w menu Konto, na ekranie Pierwsze kroki lub w checklistie kampanii) — prowadzi do `cal.com/speaklouder/30min`. Wdrożenie pomożemy skonfigurować bezpłatnie.

**24. Wpisuję adres i wyrzuca mnie na dashboard.**
Nieznane adresy są przekierowywane do `/dashboard`. Sprawdź, czy link jest poprawny — pełną mapę ścieżek masz w sekcji 7.

**25. Czy jedno konto może obsługiwać wiele firm/klientów (agencja)?**
Domyślnie konto = jedna organizacja. Dla agencji obsługujących wielu klientów istnieje tryb agencyjny (white-label) — status widać w Ustawienia → Agencja; o taki dostęp można poprosić (plik 04).

**26. W jakich językach mówi agent i skąd wiem, jak brzmi?**
Głos wybierasz z gotowych próbek w zakładce Agent i możesz go odsłuchać przed zapisaniem. Zanim ruszysz z prawdziwymi leadami, zawsze przetestuj agenta rozmową w przeglądarce — to darmowe i pokazuje realny efekt (plik 02).

**27. Czy agent dzwoni całą dobę?**
Agent dzwoni tylko w oknie i dniach ustawionych w harmonogramie kampanii (Workflow). Poza tym oknem połączenia się nie odbywają. Połączenia przychodzące agent może odbierać zgodnie z konfiguracją (plik 03).

**28. Zależy mi na szybkim starcie — od czego zacząć?**
1) Załóż/zaloguj konto → 2) „Nowa kampania" i wybór typu źródła → 3) skonfiguruj agenta (kreator AI) → 4) przetestuj w przeglądarce → 5) podłącz źródło leadów → 6) zweryfikuj firmę (KYB) i kup numer → 7) doładuj kredyty → 8) uruchom. Kroki 3–4 są darmowe; płacisz od realnych rozmów.

### Szybka ściąga „gdzie znajdę X"
| Chcę… | Idź do |
|---|---|
| Zobaczyć saldo / doładować kredyty | Górny pasek (monety) lub Ustawienia → Kredyty (`?tab=billing`) |
| Sprawdzić cennik | Ustawienia → Cennik (`?tab=cennik`) |
| Zweryfikować firmę (KYB) | Ustawienia → Weryfikacja (`?tab=weryfikacja`) |
| Kupić numer telefonu | Numery telefonów → Kup numer |
| Ustawić głos i skrypt agenta | Kampania → Agent |
| Zmienić kolejność telefonów/SMS/e-maili | Kampania → Workflow |
| Wgrać leady z pliku | Kampania → Źródło (typ CSV) |
| Zobaczyć nagrania i transkrypcje | Kampania → Aktywność → Połączenia |
| Zobaczyć historię wszystkich akcji | Kampania → Aktywność → Dziennik akcji |
| Podłączyć Gmaila / kalendarz / Make | Integracje |
| Zmienić hasło / motyw / dostęp supportu | Ustawienia → Konto |
| Umówić pomoc z człowiekiem | „Umów spotkanie z ekspertem" (cal.com) |

### Dodatkowe obiekcje sprzedażowe (z odpowiedziami)
- **„Nie mam czasu tego konfigurować."** → Kreator AI generuje prompt na podstawie kilku pytań o firmę, a ekspert pomoże za darmo na spotkaniu. Start bywa kwestią kilkunastu minut.
- **„Boję się, że agent powie coś nie tak."** → Skrypt (prompt) w pełni kontrolujesz, a przed startem testujesz rozmowę w przeglądarce bez kosztów. Każda rozmowa jest nagrana i podsumowana, więc masz pełną kontrolę.
- **„Mam mało leadów, to się nie opłaca."** → Nie ma abonamentu za samo korzystanie — płacisz tylko za realne rozmowy i numer. Nawet mała baza może na tym zyskać (szybszy kontakt = wyższa konwersja).
- **„Wolę najpierw zobaczyć, jak to działa."** → Test agenta w przeglądarce jest darmowy i nie wymaga weryfikacji ani numeru. Można też umówić bezpłatne demo z ekspertem.

---

## Wersja aplikacji

Obowiązuje nowy interfejs („SpeakLouder v2", `apps/dashboard`). W okresie migracji ze starego frontendu może pojawić się baner informacyjny (np. „30 dni" / „Wyłącz nowy widok"). Ta baza wiedzy opisuje **nowy widok (v2)** — jeśli klient opisuje ekrany zupełnie niepasujące do tego opisu, prawdopodobnie korzysta jeszcze ze starego widoku i warto zaproponować przejście na nowy.
