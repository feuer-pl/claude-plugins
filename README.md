# Feuer — pluginy Claude

Obsługa treści serwisu Feuer.pl rozmową w czacie Claude: plugin zawiera dokumentację serwisu (skill `cms`) i konektor do serwera serwisu. Operacje wykonują się na własnym koncie WordPressa osoby, która się zaloguje — w granicach jego uprawnień.

Zawartość repozytorium jest generowana automatycznie z dokumentacji serwisu — zmiany wprowadzone tutaj ręcznie zostaną nadpisane.

| Plugin | Serwer | Konektor |
|---|---|---|
| `feuer-dev` — „Feuer (dev)" | serwer dev (testowy) | „Feuer CMS (dev)" |

## Wymagania

- Konto Claude na płatnym planie (Pro, Max, Team albo Enterprise).
- W Claude włączone „Code execution and file creation": Settings → Capabilities.
- Własne konto WordPressa w serwisie.

Konto GitHub nie jest potrzebne.

## Instalacja

W Claude w przeglądarce albo w aplikacji desktopowej:

1. Customize → Plugins → „Add" → „Add marketplace".
2. W polu „URL" wpisz `feuer-pl/claude-plugins`. Przełącznik „Sync automatically" zostaw włączony — nowe wersje pluginu będą docierać same. Zatwierdź przyciskiem „Sync".
3. Zakładka „Discover", blok „New plugins": przy „Feuer (dev)" wybierz „+".

## Podłączenie konektora

1. Otwórz plugin „Feuer (dev)" → zakładka „Connectors" → przy konektorze („Not added") wybierz „Connect".
2. Okno „Add custom connector": nazwa i adres są już wpisane → „Continue". Na następnym ekranie zostaw zaznaczone „Sign in now" i „Use Claude's published identity" → „Add".
3. Ekran logowania WordPressa: zaloguj się własnym kontem serwisu (na zalogowanie jest 60 sekund) → na ekranie zgody wybierz „Zezwól" → powrót do Claude. Konektor ma stan „Connected".

Plugin i konektor dodane w przeglądarce działają także w aplikacji desktopowej i na telefonie, na tym samym koncie Claude.

## Użycie

W nowej rozmowie opisz, co chcesz zrobić w serwisie — Claude sam sięgnie po skill i konektor. Skill można też wybrać ręcznie: wpisz `/` i wybierz `cms`. Przy pierwszym użyciu konektora Claude prosi o zgodę („Allow once").

## Odłączenie

- Konektor: Customize → Connectors → konektor → „Disconnect".
- Dostęp po stronie serwisu: w panelu WordPressa Użytkownicy → profil konta → „Hasła aplikacji" → „Unieważnij" przy wpisie „Claude".
