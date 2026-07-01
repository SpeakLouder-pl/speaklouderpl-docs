# SpeakLouder — KB dla agenta AI (2/4): Kampanie i Agent

## Lista kampanii (`/dashboard/campaigns`)

Na górze podsumowanie: liczba wszystkich kampanii (i ile aktywnych), wykonane połączenia, łączne leady (i zakwalifikowani), średnia skuteczność (zakwalifikowani / wszyscy).

Tabela „Wszystkie kampanie": każdy wiersz = nazwa, **typ** (źródło leadów), **status**, liczba leadów, przycisk **Szczegóły** (wchodzi do kampanii). Statusy kampanii:
- **Aktywna** — agent dzwoni zgodnie z workflow.
- **Wstrzymana** — kampania istnieje, ale agent nie dzwoni.

## Tworzenie kampanii

Przycisk **Nowa kampania** (menu po lewej lub górne). Kroki:
1. **Wybierz typ kampanii** (modal „Wybierz typ kampanii") — decyduje wyłącznie o źródle leadów:
   - **HTTP Webhook** — leady wpadają automatycznie żądaniem POST z zewnętrznego systemu (formularz, Make.com, Zapier, własny backend).
   - **Shopify** — automatyczne dzwonienie do klientów z porzuconym koszykiem w sklepie Shopify.
   - **CSV Upload** — jednorazowy/okresowy import z pliku (arkusz kalkulacyjny).
   - **Meta Forms** — leady z reklam Facebook/Instagram; oznaczone **Wkrótce**, niedostępne.
2. Kliknij **Dalej**.
3. **Nazwij kampanię** i kliknij **Utwórz kampanię**.
4. Trafiasz na **Pierwsze kroki** tej kampanii.

## Pierwsze kroki kampanii (`/campaigns/:id/get-started`)

Checklista (każdy punkt to karta z linkiem do właściwej zakładki):
1. **Skonfiguruj agenta** — głos i styl rozmowy.
2. **Ustaw workflow** — scenariusz kampanii.
3. **Przetestuj agenta** — rozmowa w przeglądarce (bez kosztów).
4. **Podłącz źródło leadów** — import/podpięcie kontaktów.
5. **Przypisz numer telefonu**.
6. **Uruchom kampanię** — dopiero teraz agent zaczyna dzwonić.
7. **Doładuj kredyty** — jeśli saldo niskie.

Na dole sekcja „Potrzebujesz pomocy?": Porozmawiaj z asystentem, Umów spotkanie z ekspertem, Otwórz dokumentację. Checklista zostaje widoczna także po ukończeniu — to punkt odniesienia; do bieżącej pracy służy zakładka **Dashboard** kampanii.

**Warunki uruchomienia kampanii:** kampania nie zadzwoni, dopóki nie ma **przypisanego numeru** i **wystarczających kredytów**. Jeśli saldo jest poniżej progu potrzebnego na rozmowę, aplikacja proponuje doładowanie zamiast startu.

## Dashboard kampanii (`/campaigns/:id/dashboard`)

KPI: Wszystkie leady, Zakwalifikowane, Wskaźnik kwalifikacji (%), Liczba połączeń. Poniżej wykres „Aktywność kampanii" (dzienny wolumen leadów i zakwalifikowanych) oraz lista „Ostatnia aktywność". W prawym górnym rogu przycisk **Zatrzymaj/Wznów kampanię**.

## Zakładka Agent (`/campaigns/:id/agent`)

To „serce" kampanii — jak agent brzmi i co mówi.

### Nowa (niezłożona) kampania — kreator

Zamiast pustych pól: ekran **„Skonfigurujmy Twojego agenta"** z przyciskiem **Zacznij konfigurację**. Kreator zadaje kilkanaście krótkich pytań o firmę i ofertę (m.in. „Jak nazywa się Twoja firma i czym się zajmuje?", „Co sprzedajesz i jaka jest cena / model sprzedaży?"). Postęp pokazywany jako „Pytanie X z N". Na podstawie odpowiedzi AI generuje gotowy **prompt** i pierwsze wypowiedzi agenta dla połączeń wychodzących i przychodzących. Alternatywa: **Pomiń i skonfiguruj ręcznie** (prawy górny róg).

### Widok po konfiguracji

Sekcje:
- **Głos** — głos agenta. Przycisk **Zmień** otwiera modal „Wybierz głos agenta" z próbkami (np. Marek, Tomek, Ania — każdy z krótkim opisem charakteru i przyciskiem „Odsłuchaj próbkę"). Wybór zapisuje **Zapisz głos**. Przy sekcji jest też „Odsłuchaj próbkę" aktualnego głosu.
- **Konfiguracja promptu** — instrukcje agenta dla połączeń wychodzących i przychodzących. Przycisk **Zarządzaj** otwiera pełny edytor promptu.
- **Oddzwanianie** — przełącznik. Gdy włączone, a klient poprosi o kontakt w innym terminie i poda godzinę, agent sam zaplanuje i wykona oddzwonienie (bez ręcznego ustawiania w workflow).
- **Narzędzia** — dostęp agenta do narzędzi, np. **kalendarza**, żeby umawiał spotkania podczas rozmowy. Kalendarz podłącza się w Integracjach (patrz plik 4); tu wybiera się go przyciskiem.
- **Baza wiedzy** — dokumenty dla agenta; oznaczone **Wkrótce**, niedostępne.

Górne przyciski:
- **Testuj agenta** — rozmowa testowa w przeglądarce, bez zużywania kredytów.
- **Wyślij połączenie** — agent dzwoni na wskazany numer (test na żywo).
- **Zarządzaj promptem** — pełny edytor treści promptu.

### Dobre praktyki (dla podpowiedzi użytkownikowi)

- Przed startem z prawdziwymi leadami zawsze **przetestować agenta** w przeglądarce.
- Prompt jest osobny dla rozmów **wychodzących** i **przychodzących** — warto dopracować oba.
- Głos dobierać do grupy docelowej; można odsłuchać próbki przed zapisem.
