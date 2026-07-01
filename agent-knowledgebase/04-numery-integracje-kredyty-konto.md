# SpeakLouder — KB dla agenta AI (4/4): Numery, Integracje, Kredyty, Konto

## Numery telefonów (`/dashboard/phone-numbers`)

Wspólna dla całego konta lista numerów, z których dzwoni agent. Na górze podsumowanie: Wszystkie numery (i ile przypisanych), Koszt miesięczny, Nieprzypisane numery, Śr. koszt na numer. Tabela „Moje numery": numer, typ (np. Mobilny), status (Aktywny), przypisana kampania, koszt miesięczny, data dodania.

### Kupno numeru (`/dashboard/phone-numbers/buy`)
Lista „Dostępne numery" z filtrem **typu** i **kraju** oraz kosztem miesięcznym w kredytach. Przycisk **Kup** dodaje numer do puli i od razu nalicza opłatę za pierwszy miesiąc. Nowy numer jest „nieprzypisany", dopóki nie wybierzesz go w kampanii.

> **WAŻNE (gating):** Kupno i zarządzanie numerami wymaga **zakończonej weryfikacji firmy (KYB)**. Bez niej widać komunikat „Zweryfikuj się" prowadzący do `/dashboard/settings?tab=weryfikacja`. Samą kampanię i agenta można przygotować oraz przetestować (rozmowa w przeglądarce) bez weryfikacji.

### Przypisanie w kampanii (`/campaigns/:id/phone`)
- **Numer przypisany:** widać numer, typ, akcje **Zmień numer** i **Odłącz** (kampania zostaje bez numeru i przestaje dzwonić).
- **Brak numeru:** pusty stan „Wybierz numer telefonu" z przyciskiem **Wybierz numer**.
- Link **Zarządzaj numerami** prowadzi do globalnej listy.

Zasada: numer należy do konta, nie do kampanii. W danym momencie obsługuje **tylko jedną** kampanię; aby użyć gdzie indziej — najpierw odłącz. Koszt miesięczny numeru jest stały, niezależny od liczby połączeń.

## Integracje (`/dashboard/integrations`)

### Integracje konta
- **Make.com** — dostępna; przycisk **Połącz**. Pozwala budować automatyzacje między SpeakLouder a setkami narzędzi (np. wysyłanie leadów przez webhook).
- **Meta Ads** — **Wkrótce**.
- **Zapier** — **Wkrótce**.

### Integracje kampanii
Sekcja „Integracje kampanii" łączy **kalendarz** lub **Gmaila**, żeby agent mógł:
- umawiać spotkania w trakcie rozmowy (kalendarz, np. Cal.com),
- wysyłać e-maile follow-up z Twojego konta (Gmail jako „poczta wychodząca").

Przycisk **Połącz integrację** dodaje nowe; przy każdej pozycji status „Połączone" i ikona kosza do usunięcia. Integrację łączy się raz na konto, a używa w kampaniach: kalendarz włącza się w zakładce **Agent** (Narzędzia), e-mail follow-up w **Workflow**.

## Kredyty i cennik (`/dashboard/settings?tab=billing` i `?tab=cennik`)

**Kredyty** to jedna waluta całego konta. Zakładka Kredyty pokazuje: **Dostępne kredyty** (z szacunkiem, na ile dni starczą przy obecnym użyciu) i **Śr. miesięczne użycie** (ostatnie 30 dni).

### Cennik (dokładne stawki)
- **Odebrana rozmowa: 6 kredytów.** Nieodebrane rozmowy i poczta głosowa — **bezpłatne**.
- **SMS: 0,4 kredytu.**
- **E-mail follow-up: bezpłatny.**
- **Numer telefonu: abonament miesięczny zależny od numeru** (rzędu 30 kredytów/mies.), naliczany od razu po zakupie.

### Doładowanie
Sekcja „Doładuj kredyty": suwak ilości kredytów (zakres ~200 do 5000+). Im więcej naraz, tym większy **bonus procentowy** (np. +5%, +10%, +15%). Podsumowanie pokazuje kupowane kredyty + bonus = łącznie oraz kwotę do zapłaty (PLN netto). Płatność **jednorazowa**, nie subskrypcja. Przykład proporcji: 1000 kredytów ≈ 1000 PLN netto (+ bonus).

## Ustawienia konta (`/dashboard/settings`)

Zakładki (przez `?tab=`): **Konto** (domyślnie), **Agencja**, **Tagi**, **Weryfikacja**, **Kredyty** (billing), **Cennik**.

### Konto (`?tab=konto`)
- **Adres email** — przypisany do konta, nie do samodzielnej zmiany.
- **Hasło** — przycisk „Wyślij link" wysyła link do resetu na e-mail konta.
- **Preferencje** — motyw jasny/ciemny.
- **Dostęp pomocy technicznej** — przełącznik pozwalający zespołowi wsparcia zajrzeć do konta przy rozwiązywaniu problemów.

### Agencja (`?tab=agencja`)
Status przypisania konta do agencji (white-label). Większość kont: „nie jest przypisane do żadnej agencji". Firmy prowadzące klientów mogą poprosić o konto agencyjne.

### Tagi (`?tab=tagi`)
Własne tagi do porządkowania leadów w CRM — nazwa (do 50 znaków) + kolor; przypisywane w karcie leada.

### Weryfikacja firmy — KYB (`?tab=weryfikacja`)
Wymagana do dzwonienia do prawdziwych leadów i kupna numerów. Realizowana przez dostawcę **Didit**. Kliknięcie „Rozpocznij weryfikację" otwiera sesję Didit w nowej karcie; wynik wraca webhookiem i odświeża status automatycznie.

Składa się z:
1. **Zgód** (checkboxy) — po zaznaczeniu i zapisaniu **nieodwracalne**:
   - Umowa Powierzenia Przetwarzania Danych (DPA),
   - Polityka Prywatności,
   - Regulamin,
   - zgoda Didit (weryfikacja),
   - potwierdzenie reprezentacji prawnej firmy,
   - zgoda AI Act.
2. **Weryfikacji firmy (KYB)** — status w polu `kyb_status` (ukończona = „Approved”). Po weryfikacji pokazywane są dane z Didit: nazwa firmy, tax number (NIP), adres.

Weryfikacja jest **kompletna**, gdy wszystkie zgody są podpisane **i** KYB = Approved. Wtedy: „Firma zweryfikowana… masz dostęp do pełnej funkcjonalności platformy".

## Najczęstsze pytania / rozwiązywanie problemów

- **Agent nie dzwoni.** Sprawdź: kampania **Aktywna** (nie Wstrzymana), **przypisany numer**, **wystarczające kredyty**, oraz czy jesteśmy w **oknie harmonogramu** (godziny + dni). Bez numeru lub przy niskim saldzie start jest blokowany.
- **Nie mogę kupić numeru.** Wymagana **zweryfikowana firma** (KYB) — dokończ w Ustawienia → Weryfikacja.
- **Nie mogę wgrać CSV.** Najpierw **zatrzymaj kampanię**, potem wgraj plik.
- **SMS wyszedł bez polskich znaków.** Treść SMS jest **tylko ASCII** — polskie znaki i emoji są automatycznie zamieniane (dla poprawnej segmentacji i kosztu).
- **Krok w sekwencji „Anulowano/Pominięto".** Patrz „Powody pominięcia kroku" w pliku 3 (np. oddzwonienie umówione, zbyt niskie zainteresowanie, brak kredytów, brak numeru/e-maila).
- **E-mail follow-up się nie wysłał.** Wymaga podłączonego **Gmaila** (poczta wychodząca) w Integracjach i włączonej opcji w Workflow.
- **Chcę tylko przetestować.** Rozmowa testowa w przeglądarce (**Testuj agenta**) i konfiguracja działają bez weryfikacji i bez kupowania numeru; nie zużywają kredytów.
- **Ile kosztuje kampania?** Płacisz za odebrane rozmowy (6 kr/szt.), opcjonalne SMS-y (0,4 kr) i abonament numeru. Nieodebrane i e-maile są darmowe.
