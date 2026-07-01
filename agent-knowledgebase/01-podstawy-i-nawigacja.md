# SpeakLouder — KB dla agenta AI (1/4): Podstawy i nawigacja

> Wewnętrzna baza wiedzy dla asystenta AI. Opisuje aplikację SpeakLouder (panel: https://app.speaklouder.pl). Nie jest publikowana na stronie dokumentacji. Język odpowiedzi do użytkownika: polski.

## Czym jest SpeakLouder

SpeakLouder to platforma z **agentem głosowym AI**, który dzwoni do leadów zamiast zespołu sprzedaży:
- prowadzi rozmowę telefoniczną (wychodzącą i przychodzącą) ustawionym głosem, według instrukcji (promptu),
- ocenia, czy lead jest zainteresowany (kwalifikacja),
- po rozmowie może automatycznie wysłać SMS lub e-mail, albo przekazać rozmowę do handlowca,
- zapisuje wszystko w prostym CRM (transkrypcja, nagranie, podsumowanie AI).

## Kluczowe pojęcia

- **Konto (organizacja)** — jedno konto użytkownika. Współdzieli kredyty, numery telefonów i integracje między wszystkimi kampaniami.
- **Kampania** — jedna grupa leadów z własną konfiguracją: źródło leadów, agent, workflow, numer telefonu, ustawienia. Praca odbywa się „wewnątrz kampanii".
- **Lead** — pojedynczy kontakt (osoba) w kampanii. Ma status, dane, historię akcji i ocenę zainteresowania.
- **Agent** — konfiguracja głosu + promptu, czyli jak AI rozmawia w danej kampanii.
- **Workflow (przepływ pracy)** — scenariusz: kiedy i jak agent kontaktuje się z leadem (sekwencja kroków, harmonogram) oraz co dzieje się automatycznie po rozmowie.
- **Kredyty** — wewnętrzna waluta konta. Płaci się nimi za odebrane rozmowy, SMS-y i abonament numerów.

## Logowanie i dostęp

- Ekrany publiczne: `/login`, `/register`, `/forgot-password`, `/reset-password`, `/auth/callback`, `/legal/:doc` (regulamin, polityka prywatności itp.).
- Logowanie e-mailem/hasłem lub przez Google (SSO).
- Obsługiwane jest **uwierzytelnianie wieloetapowe (MFA/2FA)** — jeśli konto ma włączony wyższy poziom (AAL2), po zalogowaniu pojawia się ekran `/mfa-challenge`.
- Po zalogowaniu `/` przekierowuje do `/dashboard`.

## Globalna nawigacja (menu po lewej)

Poza kampanią menu zawiera:
- **Nowa kampania** (przycisk u góry) — start tworzenia kampanii.
- **Pierwsze kroki** — `/dashboard/get-started` (globalny onboarding konta).
- **Dashboard (Przegląd)** — `/dashboard`.
- **Kampanie** — `/dashboard/campaigns`.
- **Baza wiedzy** — oznaczone „Wkrótce" (funkcja w przygotowaniu).
- **Numery telefonów** — `/dashboard/phone-numbers` (rozwija: Moje numery, Kup numer).
- **Integracje** — `/dashboard/integrations`.
- Sekcja **Konto**: „Umów spotkanie z ekspertem" (link do cal.com), **Ustawienia** (`/dashboard/settings`), **Pomoc** (link do dokumentacji).

Wewnątrz kampanii menu zmienia się na zakładki tej kampanii (patrz plik 2 i 3): Pierwsze kroki, Dashboard, Leady, Źródło, Workflow, Agent, Numer telefonu, Aktywność (Połączenia, Dziennik akcji), Ustawienia kampanii. W lewym górnym rogu jest rozwijana lista do **przełączania między kampaniami**.

## Górny pasek (na każdej stronie)

- **Licznik kredytów** — aktualne saldo; klik prowadzi do `/dashboard/settings?tab=billing`.
- **Ikona ✨ Asystent AI** — otwiera asystenta AI, który pomaga w obsłudze panelu (konfiguracja kampanii/agenta, analiza leadów, strategia kontaktu). Dostępny z każdego ekranu.
- **Ikona motywu** — przełącza wygląd jasny/ciemny.

## Pełna mapa routingu (URL-e)

Poziom konta:
- `/dashboard` — Przegląd (podsumowanie wszystkich kampanii).
- `/dashboard/get-started` — pierwsze kroki konta.
- `/dashboard/analytics` — Analityka (łączne leady, zakwalifikowani, połączenia, aktywne kampanie oraz rozkłady statusów leadów i kampanii).
- `/dashboard/campaigns` — lista kampanii.
- `/dashboard/integrations` — integracje.
- `/dashboard/knowledgebase` — Baza wiedzy (Wkrótce).
- `/dashboard/phone-numbers` — numery (Moje numery).
- `/dashboard/phone-numbers/buy` — kupno numeru.
- `/dashboard/settings` — ustawienia; zakładki przez `?tab=`: `konto` (domyślnie), `agencja`, `tagi`, `weryfikacja`, `billing` (Kredyty), `cennik`.

Poziom kampanii (`:id` = identyfikator kampanii):
- `/dashboard/campaigns/:id` → przekierowuje do `get-started`.
- `/dashboard/campaigns/:id/get-started` — checklista pierwszych kroków kampanii.
- `/dashboard/campaigns/:id/dashboard` — dashboard kampanii (KPI, wykres, ostatnia aktywność).
- `/dashboard/campaigns/:id/agent` — konfiguracja agenta.
- `/dashboard/campaigns/:id/agent/knowledgebase` — baza wiedzy agenta (Wkrótce).
- `/dashboard/campaigns/:id/workflow` — przepływ pracy.
- `/dashboard/campaigns/:id/source` — źródło leadów.
- `/dashboard/campaigns/:id/leads` — CRM (lista leadów).
- `/dashboard/campaigns/:id/leads/:leadId` — karta leada.
- `/dashboard/campaigns/:id/activity` → przekierowuje do `activity/calls`.
- `/dashboard/campaigns/:id/activity/calls` — połączenia z transkrypcją.
- `/dashboard/campaigns/:id/activity/action-log` — dziennik akcji.
- `/dashboard/campaigns/:id/phone` — numer telefonu kampanii.
- `/dashboard/campaigns/:id/settings` — ustawienia kampanii.

Nieznane ścieżki przekierowują do `/dashboard`.

## Wersja aplikacji

Obowiązuje nowy widok („SpeakLouder v2"). Na górze bywa baner „Witaj w SpeakLouder v2" z opcją „Wyłącz nowy widok". KB opisuje wersję v2.
