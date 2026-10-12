# Feuer — pluginy Claude

Obsługa treści serwisu Feuer.pl rozmową w czacie Claude: plugin zawiera dokumentację serwisu (skill `cms`) i konektor do serwera serwisu. Operacje wykonują się na własnym koncie WordPressa osoby, która się zaloguje — w granicach jego uprawnień.

Zawartość repozytorium jest generowana automatycznie z dokumentacji serwisu — zmiany wprowadzone tutaj ręcznie zostaną nadpisane.

| Plugin | Serwer | Konektor |
|---|---|---|
| `feuer-dev` — „Feuer (dev)" | serwer dev (testowy) | „Feuer CMS (dev)" |

## Instalacja i podłączenie konektora

Wymagania, instalacja pluginu i podłączenie konektora — krok po kroku, ze zrzutami ekranu: [lekcja „Instalacja pluginu Claude i podłączenie konektora"](https://feuer-dev.duckdns.org/samouczek/b/instalacja-pluginu-claude/).

## Użycie

W nowej rozmowie opisz, co chcesz zrobić w serwisie — Claude sam sięgnie po skill i konektor. Skill można też wybrać ręcznie: wpisz `/` i wybierz `cms`. Przy pierwszym użyciu konektora Claude prosi o zgodę („Allow once").

## Aktualizacja

Samoczynna synchronizacja w Claude obecnie nie działa — po zmianach w serwisie zrób dwa kroki:

1. Nowa wersja pluginu. W Claude w przeglądarce (w aplikacji desktopowej ta funkcja zgłasza błąd): Customize → Plugins → „Add" → „Manage marketplaces" → przy `claude-plugins` menu „⋮" → „Check for updates".
2. Nowe operacje serwisu. Customize → Connectors → konektor → menu „⋮" → „Refresh tools list" — bez tego Claude pracuje ze starą listą operacji.

Którą wersję pluginu masz, sprawdzisz w rozmowie: zapytaj o wersję, np. `/cms jaka jest wersja pluginu?`. Numer widać też na stronie pluginu, pod jego nazwą.

## Odłączenie

- Konektor: Customize → Connectors → konektor → „Disconnect".
- Dostęp po stronie serwisu: w panelu WordPressa Użytkownicy → profil konta → „Hasła aplikacji" → „Unieważnij" przy wpisie „Claude".
