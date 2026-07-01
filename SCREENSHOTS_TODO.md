# Brakujące screenshoty

Nie mogłem automatycznie zapisać zrzutów ekranu jako plików w tej sesji (Chrome działa poza moim sandboxem). Poniżej pełna lista obrazków, które trzeba dorobić i wrzucić do `images/` pod wskazaną nazwą. Każdy wpis mówi dokładnie, jaki URL otworzyć i w jakim stanie ma być ekran.

Zostawiłem w koncie testową kampanię **"Dokumentacja - test"** (typ: CSV Upload) — jest specjalnie nieskonfigurowana, żeby dało się z niej zrobić zrzuty pustych/onboardingowych stanów (agent-onboarding-*, numer-pusty-stan, zrodlo-csv, kampania-pierwsze-kroki). Możesz ją potem usunąć.

| Plik docelowy | URL | Stan ekranu |
| --- | --- | --- |
| `dashboard-overview.png` | `/dashboard` | Widok domyślny po zalogowaniu |
| `kampanie-lista.png` | `/dashboard/campaigns` | Lista z co najmniej 2 kampaniami, różne statusy |
| `kampania-wybierz-typ.png` | `/dashboard/campaigns` | Po kliknięciu "Nowa kampania" — modal wyboru typu |
| `kampania-pierwsze-kroki.png` | `/dashboard/campaigns/{id}/get-started` | Świeża kampania "Dokumentacja - test", checklist widoczny |
| `agent-onboarding-start.png` | `.../agent` (kampania "Dokumentacja - test") | Ekran "Skonfigurujmy Twojego agenta" przed startem |
| `agent-onboarding-pytanie.png` | `.../agent` | W trakcie kreatora, "Pytanie 1 z 14" |
| `agent-skonfigurowany.png` | `.../agent` (kampania "Demo" lub "SpeakLouder 1") | Widok po konfiguracji, od góry |
| `agent-wybor-glosu.png` | `.../agent` | Modal "Wybierz głos agenta" otwarty |
| `workflow-gora.png` | `.../workflow` | Sekcje Sekwencja kontaktów + Harmonogram |
| `workflow-automatyzacje.png` | `.../workflow` | Sekcja SMS/e-mail/transfer, jeden wiersz rozwinięty |
| `zrodlo-webhook.png` | `.../source` (kampania typu HTTP Webhook) | Adres webhooka + token |
| `zrodlo-csv.png` | `.../source` (kampania "Dokumentacja - test") | Strefa "Upuść plik CSV tutaj" |
| `crm-lista.png` | `.../leads` (kampania "SpeakLouder 1") | Lista leadów z różnymi statusami |
| `lead-karta-pulpit.png` | `.../leads/{leadId}` | Zakładka "Pulpit" z analizą AI |
| `lead-karta-sekwencja.png` | `.../leads/{leadId}` | Zakładka "Sekwencja" z krokami |
| `aktywnosc-polaczenia.png` | `.../activity/calls` | Zaznaczone połączenie z transkrypcją |
| `aktywnosc-dziennik.png` | `.../activity/action-log` | Historia kilku różnych akcji |
| `numer-przypisany.png` | `.../phone` (kampania "Demo") | Numer przypisany, widok domyślny |
| `numer-pusty-stan.png` | `.../phone` (kampania "Dokumentacja - test") | Pusty stan, przycisk "Wybierz numer" |
| `kampania-ustawienia.png` | `.../settings` | Ogólne + Powiadomienia + Strefa niebezpieczna |
| `numery-moje.png` | `/dashboard/phone-numbers` | Zakładka "Moje numery" |
| `numery-kup.png` | `/dashboard/phone-numbers/buy` | Lista numerów do kupienia |
| `integracje-strona.png` | `/dashboard/integrations` | Integracje konta + integracje kampanii |
| `ustawienia-kredyty.png` | `/dashboard/settings?tab=billing` | Saldo, doładowanie, transakcje |
| `ustawienia-konto.png` | `/dashboard/settings` | Zakładka "Konto" |

Po dodaniu plików do `images/` żadna zmiana w treściach `.mdx` nie jest potrzebna — ścieżki już na nie wskazują.
