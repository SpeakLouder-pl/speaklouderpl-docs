# SpeakLouder — pełna baza wiedzy (KB) dla wewnętrznego asystenta AI

> **Wewnętrzna baza wiedzy dla asystenta AI SpeakLouder (support + sprzedaż).** Ten plik NIE jest publikowany na stronie dokumentacji — to materiał referencyjny dla asystenta, który ma znać odpowiedź na wszystko: co to jest, gdzie się co ustawia, jak, ile kosztuje i jak to sprzedać. Panel aplikacji: `https://app.speaklouder.pl`. Dokumentacja publiczna: `https://docs.speaklouder.ai`. Umówienie eksperta: `https://cal.com/speaklouder/30min`. **Język odpowiedzi do użytkownika: zawsze polski.**
>
> Ten dokument powstał z połączenia czterech modułów wiedzy w jeden plik. Struktura:
> - **Część 1 — Podstawy i nawigacja** (czym jest SpeakLouder, słownik, logowanie, mapa routingu, jak pomagać, FAQ podstaw).
> - **Część 2 — Kampanie i Agent** (lista i tworzenie kampanii, uruchamianie, dashboard kampanii, zakładka Agent, pisanie promptu, testy).
> - **Część 3 — Workflow, Leady, Aktywność** (przepływ pracy, źródło leadów, CRM, karta leada, aktywność, powody pominięcia kroków).
> - **Część 4 — Numery, Integracje, Kredyty, Konto, Weryfikacja (KYB)**.
>
> Odwołania w tekście typu „Część 2/3/4" wskazują odpowiedni rozdział poniżej.

---

# CZĘŚĆ 1 — Podstawy i nawigacja

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
- Odebrana rozmowa kosztuje **6 kredytów** (≈ 6 PLN netto przy proporcji ~1 kredyt ≈ 1 PLN, patrz Część 4). Nieodebrane rozmowy i poczta głosowa są **bezpłatne**.
- Przy koszcie kilku złotych za rozmowę i kwalifikacji dziesiątek leadów dziennie, koszt jednego zakwalifikowanego leada bywa niższy niż godzina pracy handlowca. Dokładne stawki i doładowania → **Część 4**.

### Jak odpowiadać na „po co mi to / czym się różni od zwykłego call center"
- **„Mam już handlowców."** → SpeakLouder ich nie zastępuje, tylko odciąża: robi pierwszy kontakt i kwalifikację, a handlowcy dostają wyłącznie gotowe leady. Więcej domkniętych transakcji przy tym samym zespole.
- **„To to samo co call center."** → Call center to koszt stały, grafik, rotacja, szkolenia i zmienna jakość. Agent AI dzwoni natychmiast, 24/7, zawsze wg skryptu, z pełną transkrypcją i oceną każdej rozmowy, a koszt jest za faktyczne rozmowy.
- **„Czy klient pozna, że to AI?"** → Głos jest naturalny (można odsłuchać próbki), a rozmowa płynna. Zawsze rekomendujemy przetestować agenta w przeglądarce przed startem — test jest darmowy.
- **„Czy to legalne / a RODO?"** → Platforma prowadzi weryfikację firmy (KYB) i wymaga akceptacji regulaminu, polityki prywatności, DPA oraz zgód AI Act przed dzwonieniem do prawdziwych leadów. Szczegóły → Część 4 i sekcja „Bezpieczeństwo" niżej.
- **„Ile to kosztuje na start?"** → Konfiguracja i testy są darmowe. Płacisz kredytami dopiero za realne rozmowy i abonament numeru. Można zacząć od małego doładowania.
- Zawsze, gdy klient chce wdrożenia „pod siebie", proponuj **bezpłatne spotkanie z ekspertem** (`cal.com/speaklouder/30min`).

---

## 2. Słownik pojęć

- **Konto (organizacja)** — jedno konto użytkownika = jedna organizacja. Współdzieli **kredyty**, **numery telefonów** i **integracje** między wszystkimi kampaniami. Wszystkie kampanie „żyją" wewnątrz jednego konta.
- **Kampania** — jedna grupa leadów z własną, odrębną konfiguracją: typ (źródło leadów), agent, workflow, przypisany numer, ustawienia. Codzienna praca odbywa się „wewnątrz kampanii". Kampania jest **Aktywna** (agent dzwoni) albo **Wstrzymana** (nie dzwoni).
- **Lead** — pojedynczy kontakt (osoba) w danej kampanii. Ma dane (imię, e-mail, telefon, pola własne), status, historię akcji i ocenę zainteresowania.
- **Agent** — konfiguracja **głosu + promptu**, czyli sposób, w jaki AI rozmawia w danej kampanii. Ustawiany osobno dla każdej kampanii. Szczegóły → Część 2.
- **Głos** — barwa/charakter mówcy agenta (np. Marek, Tomek, Ania). Wybiera się z gotowych próbek; można odsłuchać przed zapisaniem.
- **Prompt** — instrukcje tekstowe dla agenta: kim jest, co ma osiągnąć, jak reagować. Osobny dla rozmów **wychodzących** i **przychodzących**. Może być wygenerowany przez kreator AI lub napisany ręcznie.
- **Workflow (przepływ pracy) / sekwencja / harmonogram** — scenariusz kampanii: jaka jest kolejność kroków (call, SMS, e-mail), z jakimi opóźnieniami, w jakich godzinach i dniach agent dzwoni oraz co dzieje się automatycznie po rozmowie. Szczegóły → Część 3.
- **Kwalifikacja** — proces oceny, czy lead jest wartościowy/zainteresowany. Domyślnie robi to AI; można podać **własny warunek zakwalifikowania** własnymi słowami.
- **Zainteresowanie leada** — ocena AI w skali **0–100**, wyliczana z treści rozmów i aktualizowana po każdym połączeniu. Nie jest polem do ręcznego wpisywania.
- **Kredyty** — wewnętrzna waluta całego konta. Płaci się nimi za odebrane rozmowy, SMS-y i abonament numerów. Doładowanie jednorazowe (nie subskrypcja). Szczegóły → Część 4.
- **Numer telefonu** — numer, z którego agent dzwoni. Należy do konta, obsługuje w danym momencie tylko jedną kampanię, ma stały abonament miesięczny. Szczegóły → Część 4.
- **Integracja** — połączenie SpeakLouder z narzędziem zewnętrznym (Make.com, Shopify, Gmail, kalendarz Cal.com). Konfigurowana na poziomie konta lub kampanii. Szczegóły → Część 4.
- **Webhook** — automatyczna wymiana danych przez HTTP POST: leady mogą wpadać do kampanii webhookiem (źródło), a dane po rozmowie mogą być wysyłane webhookiem do zewnętrznego systemu.
- **Token** — sekretny klucz w adresie webhooka źródła leadów, identyfikujący kampanię. Traktować jak hasło — nie ujawniać publicznie (w komunikacji token w URL zawsze maskujemy/blurujemy).
- **Weryfikacja / KYB** — weryfikacja firmy (Know Your Business) przez dostawcę **Didit**. Wymagana do dzwonienia do prawdziwych leadów i kupna numerów. Szczegóły → Część 4.
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
- Alternatywnie: w **Ustawieniach → Konto** jest przycisk „Wyślij link", który wysyła link resetu na e-mail konta (patrz Część 4).

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

Nieznany slug pokazuje „Nie znaleziono dokumentu". Dokumenty prawne akceptuje się także w procesie weryfikacji firmy (Część 4).

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
| **Pierwsze kroki** | `/campaigns/:id/get-started` | Checklista uruchomienia kampanii (Część 2). |
| **Dashboard** | `/campaigns/:id/dashboard` | KPI kampanii, wykres, ostatnia aktywność (Część 2). |
| **Leady** | `/campaigns/:id/leads` | CRM — lista leadów (Część 3). |
| **Źródło** | `/campaigns/:id/source` | Konfiguracja źródła leadów (Część 3). |
| **Workflow** | `/campaigns/:id/workflow` | Sekwencja, harmonogram, automatyzacje (Część 3). |
| **Agent** | `/campaigns/:id/agent` | Głos i prompt agenta (Część 2). |
| **Numer telefonu** | `/campaigns/:id/phone` | Przypisanie numeru (Część 4). |
| **Aktywność** | `/campaigns/:id/activity/calls` | Rozwija: **Połączenia** i **Dziennik akcji** (Część 3). |

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

Ten ekran to najlepszy punkt startu dla nowego użytkownika. Onboarding wewnątrz konkretnej kampanii (checklista 6–7 kroków) opisano w Części 2.

---

## 10. Jak asystent AI powinien pomagać

### Ton i zasady
- **Zawsze po polsku**, rzeczowo, krótko i konkretnie. Bez lania wody i bez emoji.
- **Najpierw ustal kontekst** — zanim doradzisz, dopytaj o to, co niezbędne: jakiego typu jest kampania (webhook/Shopify/CSV/Meta), na jakim jest etapie (skonfigurowana? uruchomiona?), czy firma jest zweryfikowana (KYB), czy ma przypisany numer i kredyty. Bez tego łatwo o błędną poradę.
- **Podawaj dokładne ścieżki** (np. „Ustawienia → Weryfikacja", `/dashboard/settings?tab=weryfikacja`) i konkretne nazwy przycisków — nie ogólniki.
- **Nie ujawniaj tokenów/sekretów** — w komunikacji token webhooka zawsze maskuj.
- **Nie obiecuj funkcji oznaczonych „Wkrótce"** (Baza wiedzy, Baza wiedzy agenta, Meta Forms, Meta Ads, Zapier) — mów wprost, że są w przygotowaniu.
- **Nie ujawniaj wewnętrznych szczegółów technicznych** (nazwy edge functions, kody statusów Supabase, surowe skip-reasony). Klientowi tłumacz je czytelnym językiem (mapowanie w Części 3).

### Kiedy kierować do dokumentacji, a kiedy do eksperta
- **Do dokumentacji** (`docs.speaklouder.ai`) — gdy klient chce samodzielnie przejść procedurę krok po kroku, którą da się opisać (konfiguracja, import CSV, integracja Make).
- **Do eksperta** (`cal.com/speaklouder/30min`) — gdy klient chce, żeby ktoś skonfigurował kampanię/agenta „pod niego", ma złożony przypadek wdrożeniowy, negocjuje warunki, albo waha się przed zakupem (kwalifikacja sprzedażowa).
- **Do supportu** — przy nieoczekiwanym komunikacie „Skontaktuj się z supportem", problemach z płatnościami, weryfikacją KYB lub podejrzeniu awarii.

### Błędy — jak rozróżnić
Jeśli klient zgłasza komunikat proszący o kontakt z supportem — to błąd serwerowy/nieoczekiwany, eskaluj (poproś o czas wystąpienia i opis). Komunikaty **wskazujące działanie** (np. „Zaloguj się ponownie", „Nie znaleziono kampanii", „Przypisz najpierw numer") to sytuacje, które klient może naprawić sam — poinstruuj go, co zrobić.

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
Kliknij „Nowa kampania" (przycisk u góry menu), wybierz typ (źródło leadów), nadaj nazwę i utwórz. Trafisz na checklistę „Pierwsze kroki". Szczegóły → Część 2.

**10. Gdzie ustawię głos i to, co mówi agent?**
Wewnątrz kampanii: zakładka „Agent". Tam wybierzesz głos i prompt (osobny dla rozmów wychodzących i przychodzących). Szczegóły → Część 2.

**11. Gdzie sprawdzę saldo kredytów?**
W górnym pasku (licznik z ikoną monety) albo w Ustawienia → Kredyty (`/dashboard/settings?tab=billing`). Doładowanie → tam samo (Część 4).

**12. Gdzie zobaczę nagrania i transkrypcje rozmów?**
Wewnątrz kampanii: Aktywność → Połączenia (`/campaigns/:id/activity/calls`). Znajdziesz tam kierunek rozmowy, wynik, długość, podsumowanie AI i pełną transkrypcję (Część 3).

**13. Gdzie są ustawienia konta?**
Menu → „Ustawienia" (`/dashboard/settings`). Zakładki: Konto, Agencja, Tagi, Weryfikacja, Kredyty, Cennik (Część 4).

**14. Jak zmienić motyw na ciemny/jasny?**
Ikoną słońca/księżyca w górnym pasku (lub w Ustawienia → Konto → Preferencje).

**15. Co to jest ikona ✨ w rogu?**
To asystent AI — pomaga we wszystkim wewnątrz panelu (konfiguracja, analiza, nawigacja, pytania o produkt). Jest dostępny z każdego ekranu.

**16. Czy moje dane są bezpieczne / a RODO?**
Tak — platforma wymaga akceptacji regulaminu, polityki prywatności i umowy powierzenia danych (DPA), a przed dzwonieniem do prawdziwych leadów przechodzi się weryfikację firmy (KYB) oraz zgody, w tym zgodę AI Act. Dostęp do konta dla supportu jest opcjonalny (przełącznik w Ustawieniach). Wspieramy też logowanie dwuetapowe (2FA). Szczegóły prawne w dokumentach `/legal/*` i w Części 4.

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
Domyślnie konto = jedna organizacja. Dla agencji obsługujących wielu klientów istnieje tryb agencyjny (white-label) — status widać w Ustawienia → Agencja; o taki dostęp można poprosić (Część 4).

**26. W jakich językach mówi agent i skąd wiem, jak brzmi?**
Głos wybierasz z gotowych próbek w zakładce Agent i możesz go odsłuchać przed zapisaniem. Zanim ruszysz z prawdziwymi leadami, zawsze przetestuj agenta rozmową w przeglądarce — to darmowe i pokazuje realny efekt (Część 2).

**27. Czy agent dzwoni całą dobę?**
Agent dzwoni tylko w oknie i dniach ustawionych w harmonogramie kampanii (Workflow). Poza tym oknem połączenia się nie odbywają. Połączenia przychodzące agent może odbierać zgodnie z konfiguracją (Część 3).

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
| Ustawić SMS / e-mail po zakwalifikowaniu (follow-up) | Kampania → **Workflow** (Ustawienia globalne) — **nie** w Ustawieniach kampanii |
| Ustawić transfer do handlowca / webhook po połączeniu / harmonogram dzwonienia | Kampania → **Workflow** |
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

---

# CZĘŚĆ 2 — Kampanie i Agent

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
- **Scenariusz sprzedażowy:** „Klient zostawia numer na landing page → w 10 sekund oddzwania agent AI, kwalifikuje i umawia spotkanie. Zero czekania, zero utraconego leada." Konfiguracja webhooka — patrz Część 3 (Źródło leadów).

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
- **Minusy:** import ręczny; **aby wgrać CSV kampania musi być zatrzymana** (patrz Część 3); to nie jest strumień „na żywo".
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

1. **Przypisany numer telefonu.** Bez numeru → dialog **„Przypisz numer telefonu"**: „Ta kampania nie ma przypisanego numeru, z którego agent dzwoni do leadów. Przypisz numer, żeby ją uruchomić." Przycisk **Przejdź do numeru** prowadzi do ustawień kampanii (tam wybiera się numer). (Zakup/przypisanie numeru wymaga zweryfikowanej firmy — patrz Część 4.)
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

Lista do 5 leadów wg ostatniego kontaktu/zmiany: nazwa + status (etykieta PL) + „ile temu". Gdy pusto — „Brak aktywności". Pełna historia — w zakładce Aktywność (Część 3).

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
- Jeśli **nie ma** połączonego kalendarza na koncie → przycisk **Przejdź do integracji** (`/dashboard/integrations`). Kalendarz łączy się raz na konto w Integracjach (patrz Część 4).
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
5. **Kwalifikacja** — po czym poznać, że lead jest zainteresowany (to steruje statusem „Zakwalifikowany"; własny warunek można też ustawić w Workflow — Część 3).
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
- Do personalizacji outbound używaj placeholderów; sprawdź, że pole istnieje w źródle (Część 3).
- Nie pakuj całej wiedzy o produkcie do promptu — trzymaj to, co potrzebne do celu rozmowy. (Dedykowana baza wiedzy dla agenta jest „Wkrótce".)
- Po każdej większej zmianie promptu zrób szybki test głosowy — brzmienie „na uchu" bywa inne niż na papierze.

---

## 8. Najczęstsze problemy i pytania (FAQ)

**1. Agent nie dzwoni.**
Sprawdź kolejno: (a) kampania jest **Aktywna** (nie Zatrzymana) — Dashboard kampanii → „Uruchom kampanię"; (b) jest **przypisany numer** (ustawienia kampanii / zakładka numeru); (c) są **kredyty** (min. próg z sekcji 4); (d) jesteś w **oknie harmonogramu** (godziny + dni — Część 3); (e) źródło ma leady. Brak numeru lub niskie saldo blokują start (patrz dialogi w sekcji 4).

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
Doładuj saldo: przycisk **Doładuj kredyty** w dialogu prowadzi do `Ustawienia → Kredyty`. Próg to najtańsza operacja w Twoim scenariuszu (patrz Część 4 — cennik).

**10. Nie mogę uruchomić — „Przypisz numer telefonu".**
Kampania nie ma numeru. Kliknij **Przejdź do numeru**, przypisz numer w ustawieniach kampanii. Numer trzeba wcześniej kupić (wymaga zweryfikowanej firmy — Część 4).

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
Najpierw połącz kalendarz na koncie: Integracje → połącz (np. Cal.com). Potem w zakładce Agent → Narzędzia → **Wybierz** pojawi się na liście (Część 4).

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

---

# CZĘŚĆ 3 — Workflow, Leady, Aktywność

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
- **Wymaga podłączonego Gmaila** — pole „źródło wysyłki (Gmail)” (`EmailSourceSelect`). Gmaila podłącza się w **Integracjach** (Część 4).
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

„Meta Lead Ads” — leady z formularzy Facebook/Instagram importowane automatycznie. W tym widoku informacja „Skonfiguruj integrację Meta na stronie Integracje” + przycisk „Przejdź do Integracji”. W praktyce integracja Meta jest oznaczona **„Wkrótce”** (patrz Część 4).

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

25. **„Gdzie ustawię SMS / e-mail wysyłany po zakwalifikowaniu leada?”** — W zakładce **Workflow** kampanii (`/campaigns/:id/workflow`), w grupie **„Ustawienia globalne”**: blok **„SMS po zakwalifikowaniu”** (limit 500 znaków, tylko ASCII) i **„E-mail po zakwalifikowaniu”** (wymaga podłączonego Gmaila). **NIE** ma tego w „Ustawieniach kampanii”. Tam samo (Workflow) ustawia się też harmonogram dzwonienia, transfer do handlowca, własny warunek zakwalifikowania i webhook po połączeniu. Ustawienia kampanii (`/campaigns/:id/settings`) służą do innych rzeczy (m.in. przypisanie numeru), a nie do automatyzacji po rozmowie.

---

### Nawigacja powiązana
- Konfiguracja agenta, prompt, głos, „Oddzwanianie”, narzędzia (kalendarz) → **Część 2**.
- Numery telefonów, Integracje (Make, Gmail, kalendarz), kredyty/cennik, weryfikacja KYB, ustawienia konta → **Część 4**.
- Podstawy, logowanie, mapa URL-i → **Część 1**.

---

# CZĘŚĆ 4 — Numery, Integracje, Kredyty, Konto, Weryfikacja (KYB)

Spis treści:
1. Numery telefonów (lista, kupno, gating KYB, przypisanie w kampanii)
2. Integracje (konto: Make.com/Meta/Zapier; kampanii: Cal.com, Gmail)
3. Kredyty i cennik (stawki, doładowanie, zamówienie, sekcja sprzedażowa)
4. Ustawienia konta (Konto, Agencja, Tagi)
5. **Weryfikacja firmy (KYB) — sekcja najobszerniejsza**
6. FAQ i troubleshooting supportowy

---

## 1. Numery telefonów (`/dashboard/phone-numbers`)

Numery są zasobem **całego konta** (nie pojedynczej kampanii). Kupujesz je do wspólnej puli, a następnie przypisujesz do konkretnych kampanii. Z przypisanego numeru agent dzwoni do leadów danej kampanii.

### 1.1. Widok „Moje numery"

Na górze cztery kafelki podsumowania:

| Kafelek | Co pokazuje |
|---|---|
| **Wszystkie numery** | Łączna liczba numerów + ile przypisanych, ile nieprzypisanych |
| **Koszt miesięczny** | Suma abonamentów wszystkich numerów w kredytach (np. „60 kr") |
| **Nieprzypisane numery** | Ile numerów jest wolnych, gotowych do przypisania |
| **Śr. koszt na numer** | Średni miesięczny koszt jednego numeru (kredyty) |

Tabela „Moje numery" — kolumny:

| Kolumna | Opis |
|---|---|
| **Numer** | Numer w formacie `+48 XXX XXX XXX` |
| **Typ** | Mobilny / Lokalny / Bezpłatny (badge) |
| **Status** | Aktywny / Nieprzypisany / Zawieszony |
| **Przypisana kampania** | Nazwa kampanii, do której numer należy (lub puste) |
| **Koszt miesięczny** | Abonament w kredytach |
| **Dodano** | Data zakupu |

Lista jest stronicowana po 10 pozycji.

#### Statusy numeru (wewnętrzne → etykieta PL)

| Wewnętrzny | Etykieta PL | Kolor | Znaczenie |
|---|---|---|---|
| `Active` | **Aktywny** | zielony | Numer przypisany do kampanii i gotowy do dzwonienia |
| `Unassigned` | **Nieprzypisany** | szary | Numer kupiony, ale nie przypięty do żadnej kampanii |
| `Suspended` | **Zawieszony** | czerwony | Numer wstrzymany (np. problem operatora / rozliczeniowy) — skontaktuj się z supportem |

### 1.2. Kupno numeru (`/dashboard/phone-numbers/buy`)

Strona „Dostępne numery" z:
- **wyszukiwarką** numeru (pole „Szukaj numeru…"),
- filtrem **typu** (obecnie dostępny **Mobilny**; „Lokalny" pojawia się w mapowaniu, ale wybór w praktyce ograniczony do mobilnych),
- filtrem **kraju** — obecnie tylko **Polska** (`PL`), pole zablokowane,
- kolumną **Koszt miesięczny** w kredytach (wartość wspólna dla listy: `monthlyLineCredits`, rzędu **~30 kredytów/mies.** — dokładna kwota widoczna przy numerze),
- przyciskiem **Kup** przy każdym numerze.

Proces zakupu (dialog potwierdzenia):
1. Klik **Kup** → dialog „Potwierdź zakup numeru" z podsumowaniem: numer, typ, koszt miesięczny.
2. **Potwierdź zakup** → stan „Kupowanie…" (nie zamykaj okna w trakcie).
3. Sukces → „Numer kupiony" — numer trafia do puli „Moje numery", **nieprzypisany**. Można go od razu przypisać do kampanii.
4. Błąd → „Zakup nie powiódł się" z komunikatem i przyciskiem **Spróbuj ponownie**.

**Ważne zasady zakupu:**
- Opłata za **pierwszy miesiąc naliczana jest od razu** po zakupie, a potem **co miesiąc** (abonament).
- Nowo kupiony numer jest **nieprzypisany** — sam z siebie nie dzwoni, dopóki nie wybierzesz go w kampanii.
- Numer schodzi z listy dostępnych po zakupie (odświeżenie listy).
- Niektóre numery mogą być nieklikalne (`buyEligible = false`) — wtedy przycisk Kup jest wyłączony.

### 1.3. GATING: kupno wymaga ukończonej weryfikacji (KYB)

To kluczowa reguła — **kupno i zarządzanie numerami jest zablokowane, dopóki firma nie przejdzie pełnej weryfikacji KYB** (`isKybComplete`). Konkretnie:

- Na `/dashboard/phone-numbers`, jeśli KYB **nie** jest ukończone:
  - przycisk w nagłówku to **„Zweryfikuj się"** (wariant outline) zamiast **„Kup numer"**, prowadzi do `/dashboard/settings?tab=weryfikacja`,
  - gdy nie masz jeszcze żadnych numerów, w miejscu tabeli pojawia się stan **„Najpierw zweryfikuj firmę"** z przyciskiem **„Przejdź do weryfikacji"**.
- Na `/dashboard/phone-numbers/buy`, jeśli KYB nie jest ukończone — cała lista jest ukryta i pokazuje się ten sam komunikat „Najpierw zweryfikuj firmę" (`Zakup numeru jest możliwy po ukończeniu weryfikacji firmy (KYB) w ustawieniach.`).

Warunek `isKybComplete` (dokładnie, z kodu): `kyb_status === "Approved"` **oraz** zaznaczone zgody `is_dpa_accepted`, `privacy_accepted`, `terms_accepted`, `didit_consent_accepted`, `ai_act_accepted`. Patrz sekcja 5.

**Co można robić BEZ weryfikacji:** budować kampanię, konfigurować agenta i workflow, wgrywać leady, oraz **testować agenta** (rozmowa w przeglądarce). Testy nie zużywają kredytów i nie wymagają numeru. Weryfikacja jest potrzebna dopiero do **kupienia numeru** i **dzwonienia do prawdziwych leadów**.

### 1.4. Przypisanie numeru w kampanii (`/dashboard/campaigns/:id/phone`)

Ekran „Numer telefonu" kampanii. W rogu przycisk **„Zarządzaj numerami"** (→ globalna lista). Stan centralny zależy od tego, czy kampania ma numer:

- **Brak numeru (pusty stan):** duży ekran „Wybierz numer telefonu" z przyciskiem **„Wybierz numer"**. Otwiera dialog z listą numerów z puli.
- **Numer przypisany:** wyświetlony numer (`+48 XXX XXX XXX`) + typ, oraz akcje:
  - **Zmień numer** — otwiera dialog wyboru z innym numerem,
  - **Odłącz** — zdejmuje numer z kampanii (kampania zostaje bez numeru i przestaje dzwonić).

Dialog wyboru pokazuje **tylko numery, które można tu przypisać**: wolne (nieprzypisane) lub już przypisane do tej samej kampanii. Jeśli pula jest pusta — komunikat „Brak wolnych numerów w puli" + przycisk **„Kup numer"**. W stopce dialogu jest też skrót **„Kup nowy numer"**.

**Zasada 1 numer = 1 kampania (w danym momencie):** numer należy do konta, ale w danej chwili obsługuje tylko jedną kampanię. Aby użyć go gdzie indziej, najpierw **odłącz** go od bieżącej kampanii. Koszt miesięczny numeru jest **stały**, niezależny od liczby połączeń i od tego, czy jest przypisany.

Podczas przypisywania/odłączania widać stan „Przypisywanie numeru…" / „Odłączanie numeru…" — trwa synchronizacja ustawień agenta, to normalne.

---

## 2. Integracje (`/dashboard/integrations`)

Strona dzieli się na dwie części: **Integracje konta** (kafelki na górze) i **Integracje kampanii** (lista poniżej).

### 2.1. Integracje konta

Trzy kafelki:

| Integracja | Status | Działanie |
|---|---|---|
| **Make.com** | Dostępna | Przycisk **Połącz** otwiera w nowej karcie zaproszenie do zainstalowania aplikacji SpeakLouder w Make.com. Pozwala budować automatyzacje (webhooki, przekazywanie leadów, integracja z setkami narzędzi). |
| **Meta Ads** | **Wkrótce** | Przycisk zablokowany. Import leadów z reklam Facebook/Instagram — w przygotowaniu. |
| **Zapier** | **Wkrótce** | Przycisk zablokowany — w przygotowaniu. |

Uwaga: pełne „połączenie" Make (status „Połączone") nie jest jeszcze wdrożone w panelu — obecnie przycisk kieruje do instalacji aplikacji w Make.com.

### 2.2. Integracje kampanii (Cal.com + Gmail)

Sekcja „Integracje kampanii" — jedna lista, do której podłączasz **kalendarz** i/lub **Gmail**. Przycisk **„Połącz integrację"** otwiera kreator z wyborem dostawcy:

- **Cal.com** — kalendarz do **umawiania spotkań** przez agenta w trakcie rozmowy.
- **Gmail** — **poczta wychodząca** do e-maili follow-up wysyłanych z Twojej skrzynki.
- **Calendly** — **Wkrótce** (zablokowane).

Limity: maksymalnie **5 integracji kalendarza** i **5 kont Gmail** (badge „Limit 5" po osiągnięciu). Każda podłączona pozycja ma badge „Połączone" i ikonę kosza do odłączenia.

#### Jak podłączyć Cal.com (krok po kroku)
1. „Połącz integrację" → wybierz **Cal.com**.
2. Podaj **Nazwę** (np. „Kalendarz sprzedaży") i **Klucz API** (`cal_live_…`). Klucz znajdziesz w Cal.com → Settings → Developer → API keys (`https://app.cal.com/settings/developer/api-keys`).
3. **Dalej** → panel pobiera **typy wydarzeń** z konta. Wybierz typ wydarzenia, dla którego agent ma umawiać spotkania (np. „Demo · 30 min").
4. **Zakończ** → integracja utworzona (klucz jest przekazywany jako narzędzie agenta w ElevenLabs).

Odłączenie Cal.com usuwa klucz API również z ElevenLabs.

#### Jak podłączyć Gmail (krok po kroku)
1. „Połącz integrację" → wybierz **Gmail**.
2. Na ekranie kreatora jest instrukcja: na ekranie zgody Google **zaznacz zgodę „Wysyłanie wiadomości e-mail w Twoim imieniu"** — bez niej agent nie wyśle wiadomości.
3. **Połącz Gmail** → OAuth Google → po powrocie na stronę integracji: toast „Gmail połączony".

Konto Gmail pojawia się na liście jako „Gmail · poczta wychodząca".

#### Częste błędy OAuth Gmail (parametr `?gmail_error=`)

| Kod | Komunikat / przyczyna |
|---|---|
| `access_denied` | Anulowano logowanie Google. |
| `gmail_send_not_granted` | Nie zaznaczono zgody na wysyłkę e-maili w Twoim imieniu — najczęstszy problem. |
| `no_refresh_token` | Google nie zwróciło tokenu odświeżania — spróbuj ponownie i zaznacz wszystkie zgody. |
| `no_email` | Nie udało się odczytać adresu Gmail. |
| `token_exchange` | Logowanie Google nie powiodło się — spróbuj ponownie. |
| `invalid_state` | Sesja logowania wygasła — spróbuj ponownie. |
| `encrypt_config` | Błąd konfiguracji serwera — skontaktuj się z nami. |
| `db` | Nie udało się zapisać połączenia — spróbuj ponownie. |
| `limit` | Osiągnięto limit 5 kont Gmail. |

### 2.3. Jak używać integracji w kampanii

Integrację łączysz **raz na konto** (w Integracjach), a **włączasz w konkretnej kampanii**:
- **Kalendarz (Cal.com)** — włącza się jako **narzędzie agenta** (zakładka **Agent → Narzędzia**), aby agent mógł umawiać spotkania w trakcie rozmowy.
- **E-mail follow-up (Gmail)** — włącza się w **Workflow** (automatyzacja „E-mail po zakwalifikowaniu"). Bez podłączonego Gmaila ta opcja nie zadziała.

### 2.4. Jak usunąć integrację
Ikona kosza przy pozycji → dialog potwierdzenia. Cal.com: „zostanie odłączony, a klucz API usunięty z ElevenLabs". Gmail: „konto przestanie wysyłać e-maile w sekwencjach".

---

## 3. Kredyty i cennik

**Kredyty** to jedna waluta całego konta — płaci się nimi za odebrane rozmowy, SMS-y i abonament numerów. Saldo widoczne jest w górnym pasku (klik → `?tab=billing`).

### 3.1. Zakładka Kredyty (`/dashboard/settings?tab=billing`)

Dwa kafelki:
- **Dostępne kredyty** — aktualne saldo. Pod spodem szacunek: „Starczy na ~X dni przy obecnym użyciu" (liczone ze średniego dziennego zużycia).
- **Śr. miesięczne użycie** — suma zużytych kredytów z ostatnich **30 dni** („Brak danych", jeśli brak historii).

Niżej: **historia transakcji** (ostatnie 5 + pełna historia w oknie). Filtry pełnej historii: **Wszystkie / Przychodzące** (zakupy) **/ Wychodzące** (zużycie).

### 3.2. Dokładny cennik (`/dashboard/settings?tab=cennik`)

Ceny pobierane są z konfiguracji (`billing_pricing`, region `poland`). Wartości bazowe:

| Akcja | Koszt | Jednostka | Uwaga |
|---|---|---|---|
| **Przeprowadzona (odebrana) rozmowa** | **6 kredytów** | za odebraną rozmowę | Płatne **tylko** za odebrane rozmowy |
| **Nieodebrana rozmowa / poczta głosowa** | **0** (za darmo) | — | Nie naliczamy za brak odpowiedzi / voicemail |
| **SMS** | **0,4 kredytu** | za SMS | Np. SMS po zakwalifikowaniu leada |
| **E-mail follow-up** | **0** (za darmo) | — | E-maile są bezpłatne |
| **Numer telefonu** | **Zależy od numeru** (rzędu ~30 kr) | miesięcznie | Abonament naliczany od zakupu i co miesiąc |

Przelicznik: **1 kredyt = 1 PLN netto** (cena bazowa, przed bonusem). Czyli odebrana rozmowa kosztuje bazowo **6 zł netto**.

### 3.3. Doładowanie kredytów (suwak + bonusy)

W zakładce Kredyty sekcja **„Doładuj kredyty"**:
- **Suwak** ilości: od **200** do **5 000+** (krok 100; techniczne maksimum suwaka 5100).
- **Bonusy procentowe** rosną wraz z ilością:

| Ilość kredytów | Bonus | Efektywna cena za rozmowę |
|---|---|---|
| < 1 000 | brak (baza) | 6,00 zł |
| ≥ 1 000 | **+5%** | 5,71 zł |
| ≥ 2 500 | **+10%** | 5,45 zł |
| ≥ 4 000 | **+15%** | 5,22 zł |

Bonusowe kredyty są „darmowe", więc obniżają **efektywny koszt jednej rozmowy** (`6 / (1 + bonus)`). Panel pokazuje przekreśloną cenę bazową i niższą cenę po bonusie oraz ile oszczędzasz na każdej rozmowie.

- **Powyżej 5 000 kredytów** — pojawia się blok **Enterprise** („Potrzebujesz więcej? Porozmawiajmy") z wyceną indywidualną i linkiem do umówienia rozmowy (`cal.com/speaklouder/30min`).
- Podsumowanie zamówienia: **Kupujesz X + Bonus (%) = Łącznie otrzymasz Y kredytów**, „Do zapłaty: Z PLN **netto**".

**Płatność jest jednorazowa (nie subskrypcja).** Kwota do zapłaty = liczba kupowanych kredytów (bez bonusu) × 1 PLN netto.

#### Przykłady wyliczeń

| Kupujesz | Bonus | Łącznie kredytów | Do zapłaty (netto) | Efektywnie / rozmowę |
|---|---|---|---|---|
| 500 | 0% | 500 | 500 zł | 6,00 zł |
| 1 000 | +5% (50) | 1 050 | 1 000 zł | 5,71 zł |
| 2 500 | +10% (250) | 2 750 | 2 500 zł | 5,45 zł |
| 4 000 | +15% (600) | 4 600 | 4 000 zł | 5,22 zł |
| 5 000 | +15% (750) | 5 750 | 5 000 zł | 5,22 zł |

### 3.4. Jak faktycznie kupić (formularz zamówienia)

Klik **„Kup … kredytów"** otwiera **formularz zamówienia** (nie płatność kartą od razu):
- Imię i nazwisko, E-mail kontaktowy (prefill z konta), Nazwa firmy, Dane do faktury (nazwa, NIP, adres).
- **Złóż zamówienie** → zapis do systemu (`credit_purchase_requests`, status „pending") i powiadomienie zespołu.
- Komunikat: „Skontaktujemy się w sprawie płatności i faktury. **Kredyty dodajemy po zaksięgowaniu wpłaty.**"

Czyli: doładowanie to zamówienie z fakturą — kredyty pojawiają się po opłaceniu. Support może przyspieszyć/pomóc, jeśli klient nie widzi kredytów po płatności.

### 3.5. Sekcja SPRZEDAŻOWA — jak rozmawiać o cenie

**Uzasadnienie ceny (koszt vs alternatywy):**
- Odebrana rozmowa to ~6 zł netto (mniej z bonusem). Nieodebrane i e-maile są **darmowe** — płacisz tylko za realny kontakt.
- Porównanie: godzina pracy handlowca/call center to koszt rzędu kilkudziesięciu–ponad stu złotych + ZUS/nadzór/rotacja. Agent AI dzwoni **równolegle, 24/7, bez przerw**, po stałej, przewidywalnej stawce za rozmowę.
- Numer to ~30 kr/mies. — koszt stały, niezależny od wolumenu połączeń.

**Jak policzyć budżet kampanii (prosty wzór):**
1. Liczba leadów × szacowany % odbieralności = liczba odebranych rozmów.
2. Odebrane rozmowy × 6 kr (lub mniej z bonusem) = koszt rozmów.
3. + (opcjonalnie) SMS-y × 0,4 kr.
4. + abonament numeru (~30 kr/mies.).
- Przykład: 500 leadów, 40% odbieralności = 200 rozmów × 6 = 1 200 kr + 1 numer 30 kr ≈ **1 230 kredytów/mies.** Kupując 2 500 (bonus +10%) klient dostaje 2 750 kr i efektywnie taniej.

**Upsell:**
- **Większe doładowanie = większy bonus** — pokaż progi 1 000 / 2 500 / 4 000 i oszczędność na rozmowie.
- **Dodatkowe numery** — więcej numerów = więcej równoległych kampanii / lepsza reputacja numerów.
- **Enterprise** (>5 000) — indywidualna oferta, kieruj do rozmowy z zespołem.

**Obiekcje cenowe + odpowiedzi:**
- *„Za drogo"* → płacisz tylko za **odebrane** rozmowy; nieodebrane i e-maile są darmowe, a koszt jest niższy niż utrzymanie handlowca.
- *„Nie wiem, ile wydam"* → koszt jest przewidywalny: 6 kr/rozmowę + abonament numeru; policzmy razem budżet na Twojej liście leadów.
- *„Wolę abonament miesięczny"* → doładowanie jest **jednorazowe**, kredyty nie wygasają nagle — płacisz za realne użycie, bez zobowiązań.
- *„Chcę fakturę / rozliczenie firmowe"* → tak, zamówienie zawiera dane do faktury; kredyty dodajemy po zaksięgowaniu.
- *„Najpierw chcę przetestować"* → test agenta w przeglądarce jest **darmowy** i nie wymaga weryfikacji ani zakupu.

---

## 4. Ustawienia konta (`/dashboard/settings`)

Zakładki (przez `?tab=`): **Konto** (domyślnie), **Agencja**, **Tagi**, **Weryfikacja**, **Kredyty** (`billing`), **Cennik**.

### 4.1. Konto (`?tab=konto`)

- **Adres email** — przypisany do konta, **nie można go zmienić** (pole zablokowane).
- **Hasło** — przycisk **„Wyślij link"** wysyła link do resetu na e-mail konta. Link ważny **30 minut**. Po wysłaniu: „Link wysłany. Sprawdź skrzynkę".
- **Preferencje → Motyw** — do wyboru **Jasny** lub **Ciemny** (dwie opcje).
- **Dostęp pomocy technicznej** — przełącznik „Zezwól wsparciu na dostęp do konta". Gdy włączony, zespół wsparcia ma podstawę, by wejść na konto i zdiagnozować/naprawić zgłoszony problem. Warto poprosić klienta o włączenie, gdy support ma pomóc.
- **Strefa niebezpieczna → Usuń konto** — trwałe, **nieodwracalne** usunięcie konta wraz z kampaniami, leadami i danymi. Wymaga potwierdzenia w dialogu.

### 4.2. Agencja (`?tab=agencja`)

Pokazuje status przypisania konta do **agencji** (model white-label). Większość kont: „Twoje konto nie jest przypisane do żadnej agencji". Jeśli konto należy do agencji — widać jej nazwę i status „Aktywna".

Blok **„Jesteś agencją?"** — zaproszenie do konta agencyjnego (biała etykieta, zaawansowane uprawnienia, dedykowane wsparcie). Kontakt przez program partnerski: `cal.com/speaklouder/speaklouder-program-partnerski`.

### 4.3. Tagi (`?tab=tagi`)

Własne tagi do porządkowania leadów w CRM:
- **Nazwa tagu** — do **50 znaków** (licznik znaków, nazwy muszą być unikalne).
- **Kolor** — wybór z gotowych presetów.
- Limit: do **50 tagów** na konto.
- Przycisk **„Dodaj tag"**; usuwanie ikoną kosza przy pozycji.

Tagi używa się w **karcie leada** (sekcja Tagi → Dodaj/Edytuj), aby segmentować leady (np. „Hot lead", „VIP").

---

## 5. WERYFIKACJA FIRMY — KYB (`/dashboard/settings?tab=weryfikacja`)

> To najważniejsza sekcja tego pliku. Weryfikacja odblokowuje kupno numeru i dzwonienie do prawdziwych leadów. Realizuje ją zewnętrzny dostawca **Didit**.

### 5.1. Po co jest weryfikacja (dlaczego wymagana)

- **Wymóg operatorów telekomunikacyjnych.** Numery są rejestrowane na SpeakLouder Sp. z o.o.; operatorzy wymagają wskazania faktycznego właściciela/użytkownika numeru. Musimy wiedzieć, jaka firma stoi za kampanią.
- **Zaufane numery i antyspam.** Weryfikacja firm ogranicza nadużycia, spam i oszustwa telefoniczne — chroni reputację numerów i skuteczność Twoich kampanii.
- **Zgodność prawna** (RODO/DPA, AI Act). Zbieramy niezbędne zgody i potwierdzenie, że osoba jest uprawniona do reprezentowania firmy.

### 5.2. Co odblokowuje, a co działa bez niej

| Funkcja | Bez weryfikacji | Po weryfikacji (KYB Approved) |
|---|---|---|
| Tworzenie kampanii, konfiguracja agenta/workflow | ✅ | ✅ |
| Wgrywanie leadów (CSV/webhook) | ✅ | ✅ |
| **Testuj agenta** (rozmowa w przeglądarce) | ✅ (za darmo, bez kredytów) | ✅ |
| **Kupno numeru telefonu** | ❌ (gating) | ✅ |
| **Dzwonienie do prawdziwych leadów** | ❌ (brak numeru) | ✅ |

### 5.3. Proces przez Didit — jak to działa technicznie

1. Klient zaznacza zgody (kroki 1 i 2) i klika **„Rozpocznij weryfikację firmy"**.
2. Panel wywołuje funkcję **`didit-kyb-create-session`**, która tworzy sesję i zwraca URL.
3. Hostowany flow Didit otwiera się w **nowej karcie** (dashboard zostaje otwarty). Klient przechodzi: **wyszukiwanie firmy + AML**.
4. Wynik wraca do SpeakLouder **webhookiem** i automatycznie odświeża status — pole **`kyb_status`** ustawia się na **`Approved`**. Nie trzeba nic klikać, status pojawi się sam.
5. Jeśli przeglądarka zablokowała nowe okno — pojawia się komunikat „Zezwól na wyskakujące okna i spróbuj ponownie".

Dane są zapisywane w tabeli `kyc_verifications` (RLS po `user_id`). Uwaga: KYB (firma) ma osobne pole `kyb_status`, niezależne od `didit_status` (który dotyczy weryfikacji tożsamości KYC).

### 5.4. Trzy kroki w interfejsie

Ekran jest wizualnym „stepperem" (kroki 1 → 2 → 3). Krok 2 jest zablokowany, dopóki nie ukończysz kroku 1; krok 3 — dopóki firma nie zostanie zatwierdzona.

- **Krok 1 — „Dokumenty i zgody":** zaakceptuj DPA, Politykę Prywatności i Regulamin. Ukończony (`step1Done`), gdy wszystkie trzy są zaznaczone.
- **Krok 2 — „Weryfikacja firmy":** zaznacz zgodę Didit i potwierdzenie reprezentacji prawnej, następnie kliknij **„Rozpocznij weryfikację firmy"**. Przycisk jest aktywny dopiero, gdy obie zgody kroku 2 są zaznaczone. Po zatwierdzeniu przez Didit widać badge **„KYB OK"** i dane firmy.
- **Krok 3 — „Deklaracja AI Act":** zaznacz deklarację zgodności z Rozporządzeniem UE 2024/1689 (AI Act).

### 5.5. WSZYSTKIE zgody — pełna lista (jednokierunkowe, nieodwracalne)

**Każda zgoda po zaznaczeniu i zapisaniu jest nieodwracalna** — checkbox zostaje zablokowany (nie da się odznaczyć w panelu). Każdemu zaznaczeniu towarzyszy zapis znacznika czasu.

| Pole (kolumna) | Krok | Nazwa / o co chodzi | Link | Timestamp |
|---|---|---|---|---|
| `is_dpa_accepted` | 1 | **Umowa Powierzenia Przetwarzania Danych (DPA)** ze SpeakLouder Sp. z o.o. — zasady przetwarzania danych osobowych w imieniu klientów | `/legal/dpa` | `dpa_accepted_at` |
| `privacy_accepted` | 1 | **Polityka Prywatności** SpeakLouder — zbieranie i przetwarzanie danych | `/legal/privacy` | `privacy_accepted_at` |
| `terms_accepted` | 1 | **Regulamin** korzystania z platformy | `/legal/terms` | `terms_accepted_at` |
| `didit_consent_accepted` | 2 | **Zgoda Didit (KYB)** — przekazanie i przetwarzanie danych firmowych (w tym dokumentów rejestrowych i danych beneficjentów rzeczywistych) przez Didit w celu weryfikacji | Polityka Didit (didit.me) | `didit_consent_accepted_at` |
| `legal_rep_confirmed` | 2 | **Potwierdzenie reprezentacji prawnej** — oświadczenie, że jesteś legalnym reprezentantem firmy i masz prawo ją zweryfikować | — | `legal_rep_confirmed_at` |
| `ai_act_accepted` | 3 | **Deklaracja AI Act (EU 2024/1689)** — zobowiązanie do zgodnego użycia systemu AI (zakaz zastosowań z Art. 5, przejrzystość i nadzór ludzki) | AI Act (EUR-Lex) | `ai_act_accepted_at` |

Kontekst AI Act pokazywany w panelu: SpeakLouder jest traktowany jako system AI wysokiego ryzyka w rozumieniu Art. 6 AI Act (automatyczne przetwarzanie głosu i decyzje w obsłudze klienta), dlatego operator składa deklarację zgodności.

### 5.6. Kiedy weryfikacja jest „kompletna"

Dwie perspektywy — obie w praktyce zbieżne:

- **Warunek techniczny odblokowania numerów** (`isKybComplete`): `kyb_status === "Approved"` **oraz** zaznaczone `is_dpa_accepted`, `privacy_accepted`, `terms_accepted`, `didit_consent_accepted`, `ai_act_accepted`.
- **Status „Weryfikacja ukończona" na ekranie** (`allDone`): firma zatwierdzona (`kyb_status === "Approved"`) **oraz** zaznaczony AI Act. Wtedy górny badge zmienia się z **„Oczekuje"** na **„Aktywna"**, a komunikat brzmi: „Firma zweryfikowana, wszystkie zgody podpisane. Masz dostęp do pełnej funkcjonalności platformy."

Uwaga: `legal_rep_confirmed` jest wymagane, by **uruchomić** weryfikację (aktywuje przycisk w kroku 2), ale nie występuje jawnie w funkcji `isKybComplete` — bo zatwierdzenie KYB przez Didit i tak zakłada, że reprezentant został potwierdzony.

### 5.7. Dane firmy pokazywane po weryfikacji

Po zatwierdzeniu, z decyzji Didit (zapisywane webhookiem) pokazujemy:
- **Nazwa firmy** (`kyb_company_name`),
- **Tax number / NIP** (`kyb_tax_number`),
- **Adres** (`kyb_company_address`).

Widać je w bloku statusu na górze zakładki oraz przy zatwierdzonym kroku 2 (badge „KYB OK", „Tożsamość firmy zweryfikowana przez Didit").

### 5.8. Statusy weryfikacji (do interpretacji dla klienta)

| `kyb_status` | Co znaczy | Co powiedzieć klientowi |
|---|---|---|
| brak / `null` | Weryfikacja nierozpoczęta | Zaznacz zgody i kliknij „Rozpocznij weryfikację firmy". |
| „w toku" (sesja otwarta, brak wyniku) | Didit jeszcze nie odesłał decyzji | Dokończ flow w karcie Didit; wynik pojawi się tu automatycznie. Odśwież stronę po chwili. |
| `Approved` | Firma zatwierdzona | Gotowe — możesz kupować numery i dzwonić. |
| odrzucona / błąd | Didit nie zatwierdził | Sprawdź poprawność danych firmy; w razie problemu uruchom weryfikację ponownie lub skontaktuj się z supportem. |

### 5.9. Weryfikacja — krok po kroku dla użytkownika

1. Wejdź w **Ustawienia → Weryfikacja** (`?tab=weryfikacja`).
2. **Krok 1:** zaznacz DPA, Politykę Prywatności i Regulamin (możesz je przeczytać z linków).
3. **Krok 2:** zaznacz zgodę Didit i potwierdzenie reprezentacji prawnej.
4. Kliknij **„Rozpocznij weryfikację firmy"** — otworzy się nowa karta Didit.
5. W Didit: wyszukaj swoją firmę i przejdź weryfikację (dane rejestrowe + AML).
6. Wróć do panelu — po chwili status zmieni się na zatwierdzony (webhook). Zobaczysz nazwę firmy, NIP i adres.
7. **Krok 3:** zaznacz deklarację AI Act.
8. Gotowe — badge „Aktywna", pełna funkcjonalność (kupno numeru, dzwonienie).

### 5.10. FAQ weryfikacja (KYB)

1. **Ile trwa weryfikacja?** Sam proces w Didit to zwykle kilka minut. Wynik wraca automatycznie webhookiem; w wyjątkowych przypadkach decyzja może zająć dłużej — odśwież stronę po chwili.
2. **Jakie dokumenty są potrzebne?** Weryfikacja opiera się na danych rejestrowych firmy (Didit wyszukuje firmę) i sprawdzeniu AML. Miej pod ręką dane firmy (nazwa, NIP) oraz informacje o reprezentacji.
3. **Czy potrzebuję firmy / NIP?** Tak — KYB (Know Your Business) dotyczy podmiotu gospodarczego. Weryfikujemy firmę i jej reprezentanta.
4. **Czy mogę cofnąć zgodę?** Nie — zgody są **jednokierunkowe**. Po zaznaczeniu i zapisaniu checkbox jest zablokowany. Kwestie wycofania danych zgłaszaj przez support (zgodnie z polityką prywatności/DPA).
5. **Dlaczego nie mogę kupić numeru?** Bo weryfikacja nie jest ukończona (`isKybComplete` = false). Dokończ wszystkie kroki w Ustawienia → Weryfikacja.
6. **Co jeśli weryfikacja jest „w toku"?** Dokończ flow w karcie Didit i odśwież stronę — wynik dojdzie webhookiem. Nie trzeba klikać ponownie.
7. **Co jeśli weryfikacja została odrzucona?** Sprawdź, czy dane firmy się zgadzają, spróbuj ponownie; jeśli nadal odrzucana — skontaktuj się z supportem.
8. **Nowa karta Didit się nie otworzyła.** Przeglądarka zablokowała wyskakujące okno — zezwól na pop-upy dla panelu i kliknij „Rozpocznij weryfikację firmy" ponownie.
9. **Przycisk „Rozpocznij weryfikację firmy" jest nieaktywny.** Musisz najpierw zaznaczyć obie zgody kroku 2 (zgoda Didit + reprezentacja prawna) — a wcześniej ukończyć krok 1.
10. **Nie widzę kroku 3 (AI Act).** Krok 3 odblokowuje się dopiero po zatwierdzeniu firmy (KYB Approved).
11. **Czy weryfikacja kosztuje kredyty?** Nie, weryfikacja jest darmowa. Kredyty zużywają dopiero rozmowy/SMS-y i abonament numeru.
12. **Kto widzi moje dane firmowe?** Dane z decyzji Didit (nazwa, NIP, adres) są zapisywane na Twoim koncie i potrzebne m.in. do rejestracji numeru na SpeakLouder u operatora.
13. **Czym różni się KYB od KYC?** KYB = weryfikacja firmy (to, co jest tu wymagane). KYC = weryfikacja tożsamości osoby. Numery odblokowuje KYB (`kyb_status`).
14. **Zaznaczyłem zgodę przez pomyłkę — jak cofnąć?** W panelu nie da się odznaczyć. Skontaktuj się z supportem, opisując sytuację.

---

## 6. FAQ i troubleshooting supportowy

### Numery
1. **Nie mogę kupić numeru / widzę „Zweryfikuj się".** Weryfikacja firmy (KYB) nie jest ukończona — dokończ w Ustawienia → Weryfikacja (patrz sekcja 5).
2. **Kupiłem numer, ale agent nie dzwoni.** Numer po zakupie jest **nieprzypisany**. Przypisz go w kampanii: `/campaigns/:id/phone` → „Wybierz numer".
3. **Chcę użyć jednego numeru w dwóch kampaniach.** Nie da się jednocześnie — 1 numer = 1 kampania w danym momencie. Odłącz go od jednej i przypisz do drugiej.
4. **Ile kosztuje numer?** Abonament miesięczny zależny od numeru (rzędu ~30 kr/mies.), naliczany od razu po zakupie i co miesiąc, niezależnie od liczby połączeń.
5. **Numer ma status „Zawieszony".** To problem po stronie operatora/rozliczeń — skontaktuj się z supportem.
6. **Brak numerów na liście „Kup numer".** Zmień filtr typu lub wyczyść wyszukiwarkę; jeśli nadal pusto — spróbuj później lub zgłoś do supportu.

### Integracje
7. **E-mail follow-up się nie wysłał.** Wymaga podłączonego **Gmaila** (poczta wychodząca) z zaznaczoną zgodą „Wysyłanie wiadomości w Twoim imieniu" oraz włączonej opcji „E-mail po zakwalifikowaniu" w Workflow.
8. **Gmail nie chce się połączyć.** Najczęściej brak zgody na wysyłkę (`gmail_send_not_granted`) — połącz ponownie i zaznacz wszystkie zgody na ekranie Google. Zobacz tabelę błędów w 2.2.
9. **Agent nie umawia spotkań.** Podłącz **Cal.com** (klucz API + typ wydarzenia) i włącz narzędzie kalendarza w Agent → Narzędzia.
10. **„Limit 5" przy integracji.** Osiągnięto maksimum 5 kalendarzy lub 5 kont Gmail — odłącz nieużywane, aby dodać nowe.
11. **Meta Ads / Zapier / Calendly niedostępne.** Te integracje mają status **Wkrótce**.

### Kredyty i płatności
12. **Doładowałem, ale nie widzę kredytów.** Doładowanie to zamówienie z fakturą — kredyty dodajemy **po zaksięgowaniu wpłaty**. Jeśli płatność została wykonana, zgłoś do supportu.
13. **Jak dostać niższą cenę za rozmowę?** Kup więcej naraz — progi bonusowe: +5% (≥1 000), +10% (≥2 500), +15% (≥4 000).
14. **Ile kosztuje kampania?** Płacisz za odebrane rozmowy (6 kr), opcjonalne SMS-y (0,4 kr) i abonament numeru. Nieodebrane rozmowy i e-maile są darmowe. Wzór budżetu w 3.5.
15. **Chcę fakturę / dane firmowe na rozliczeniu.** Formularz zamówienia zawiera pole „Dane do faktury" (nazwa, NIP, adres).
16. **Kredyty mi się kończą — na ile starczy?** Zakładka Kredyty pokazuje szacunek „Starczy na ~X dni" na podstawie średniego zużycia z 30 dni.
17. **Potrzebuję dużego wolumenu (>5 000 kredytów).** To oferta Enterprise — umów rozmowę (link w sekcji doładowania) po wycenę indywidualną.

### Konto
18. **Nie mogę zmienić e-maila.** Adres e-mail jest przypisany do konta na stałe i nie można go zmienić w panelu.
19. **Zapomniałem hasła / chcę zmienić hasło.** Ustawienia → Konto → Hasło → „Wyślij link" (link ważny 30 minut).
20. **Support prosi o dostęp do konta.** Włącz „Dostęp pomocy technicznej" w Ustawienia → Konto, aby zespół mógł zajrzeć i naprawić problem.
21. **Chcę usunąć konto.** Ustawienia → Konto → Strefa niebezpieczna → Usuń konto. Akcja jest **nieodwracalna** (usuwa kampanie, leady, dane).
22. **Jesteśmy agencją / chcemy white-label.** Ustawienia → Agencja → „Jesteś agencją?" → umów się przez program partnerski.

### Błędy (dla supportu)
Interfejs nie pokazuje technicznych komunikatów Supabase/Edge. Klient widzi **komunikat akcji** — czytelny opis, co zrobić. Jeśli komunikat prosi o kontakt z supportem, to błąd serwerowy/nieoczekiwany — eskaluj (poproś o czas wystąpienia i opis sytuacji), bo to nie jest problem po stronie użytkownika.

Przykłady komunikatów akcji: `Unauthorized` → „Zaloguj się ponownie", `insufficient_balance` → za mało kredytów (w kupnie numeru), `no_campaign_phone` → „Najpierw przypisz numer do kampanii".
