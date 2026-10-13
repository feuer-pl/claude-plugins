# feuer/sprawdz-takze

„Sprawdź także" — wiersz z etykietą i linkiem do jednego wpisu serwisu (artykułu, strony, szkolenia). Typ: T ([bloki.md](bloki.md), „Typy bloków"); element palety treści redakcyjnej ([paleta-tresci.md](paleta-tresci.md), [xvmx4u]).

## Pola

| ID | Pole | Atrybut | Rodzaj | Dozwolone | Limit | Wymagane / domyślne |
|---|---|---|---|---|---|---|
| **[jxsgb2]** | Etykieta (w całości pogrubiona — `strong`) | `etykieta` | tekst z łamaniem wiersza (Shift+Enter), w miejscu | „Krótki tekst" ([bloki.md](bloki.md), [nmwmdu], [taeeq4]); bez linków | — | pusta (także same łamania i spacje, w tym twarde) — „Sprawdź także:" przez i18n |
| **[ecp92t]** | Link | `link`: `id` (ID wpisu), `typ` (typ wpisu — podgląd tytułu w edytorze), `url` (adres z chwili wyboru — wyłącznie do edytora) | kontrolka linku: wyłącznie wybór wpisu serwisu — bez własnego adresu (`noDirectEntry`) i ustawień linku; „Usuń" zeruje link | jeden wpis serwisu | — | pusty |

## Dane

- **[m3hpp9]** Render: `link.id` rozwiązany na wpis w bieżącym języku; adres i tekst linku — z tego wpisu (tekst = tytuł wpisu; zmiana tytułu przenosi się sama). Bez wskazanego wpisu albo wpis nieopublikowany — blok nie renderuje się na froncie.

## Edytor

- **[kc443n]** W kanwie jak na froncie: etykieta widoczna od razu; wybór wpisu otwiera się po wstawieniu (i przy każdym wczytaniu bloku bez wpisu), później — kliknięciem w link; bez wpisu link ma tekst „Wybierz wpis…"; tytuł linku — z rekordu wpisu.

## Przykład

```html
<!-- wp:feuer/sprawdz-takze {"link":{"id":42,"typ":"post","url":"https://feuer.pl/baza-wiedzy/…/"}} /-->
```
