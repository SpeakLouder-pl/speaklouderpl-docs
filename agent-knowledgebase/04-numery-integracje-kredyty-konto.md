# SpeakLouder — KB dla agenta AI (4/4): Numery, Integracje, Kredyty, Konto, Weryfikacja

> Wewnętrzna baza wiedzy dla asystenta AI (support + sprzedaż). Nie jest publikowana na stronie dokumentacji. Język odpowiedzi do użytkownika: **polski**. Ten plik jest źródłem prawdy w temacie **kredytów/cennika** oraz **weryfikacji firmy (KYB)**. Gdy pojawia się token w adresie URL — **maskuj go** przy pokazywaniu użytkownikowi.

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

### Kody błędów (dla supportu)
Interfejs nie pokazuje technicznych komunikatów Supabase/Edge. Widać albo **komunikat akcji** („Błąd. <co zrobić>", bez kodu), albo **kod supportowy** („Błąd E1xxx. Skontaktuj się z supportem"):

| Kod | Znaczenie |
|---|---|
| **E1001** | Wywołanie funkcji Edge nie powiodło się (non-2xx / sieć) |
| **E1003** | Błąd HTTP bez czytelnego pola `error` |
| **E1203** | Ogólny błąd serwera / bazy / edge |
| **E1204** | Przekroczono limit zapytań / przeciążenie (spróbuj później) |

Przykłady komunikatów akcji (bez kodu): `Unauthorized` → „Zaloguj się ponownie", `insufficient_balance` → za mało kredytów (w kupnie numeru), `no_campaign_phone` → „Najpierw przypisz numer do kampanii".

Gdy klient podaje kod E12xx — poproś o czas wystąpienia i eskaluj; to błędy serwerowe, nie po stronie użytkownika.
