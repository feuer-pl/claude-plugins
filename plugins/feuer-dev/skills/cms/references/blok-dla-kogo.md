# feuer/dla-kogo

„Dla kogo" — sekcja na tle wyróżnionym: nagłówek, lead, podpis i rząd numerowanych pozycji ([feuer/dla-kogo-pozycja](blok-dla-kogo-pozycja.md)). Typ: T ([bloki.md](bloki.md), „Typy bloków"); reguły wspólne pozycji: [bloki.md](bloki.md), „Pozycje".

## Gdzie

- **[uu8tyb]** Samodzielna sekcja pełnej szerokości w treści stron i produktów, poza paletą treści redakcyjnej — strefy treści bloków jej nie przyjmują.

## Pola

| ID | Pole | Atrybut | Rodzaj | Dozwolone | Limit | Wymagane / domyślne |
|---|---|---|---|---|---|---|
| **[4frs8w]** | Nagłówek (H2, w całości ExtraBold) | `tytul` | tekst z łamaniem wiersza | „Akcent w nagłówkach — bez akcentu" ([bloki.md](bloki.md), [bmw7u4]) | 60 | obowiązkowe |
| **[bzrp29]** | Lead | `lead` | tekst z łamaniem wiersza | pogrubienie | 200 | obowiązkowe |
| **[kqtg8d]** | Podpis (Bold z CSS) | `podpis` | tekst jednowierszowy | bez formatów | 60 | obowiązkowe |
| **[gn8sv6]** | Pozycje | bloki wewnętrzne | `feuer/dla-kogo-pozycja` | wyłącznie `feuer/dla-kogo-pozycja` | „Liczba pozycji" w toolbarze bloku ([bloki.md](bloki.md), [4dtarj], [edg7dw]) | po wstawieniu 4 |

- **[j233hx]** Numer pozycji („01.", „02." …) — automatycznie z licznika CSS, bez znaczników w treści.

## Warianty

- **[uutjmd]** Jeden komponent: liczba pozycji i tytuł pozycji to parametry treści, nie odmiany; odmiany ikonowej (ikony zamiast numerów) nie ma — sekcję z ikonami składa Proces współpracy albo treść redakcyjna.

## Dane

- **[4fn52g]** Skład: sekcja na tle wyróżnionym (`tlo-wyroznione`) — nagłówek H2, lead, podpis, lista numerowana (`ol`) pozycji.
- **[pv87q2]** Wyrównanie wierszy opisów — zawsze, bez przełącznika: gdy któryś opis pozycji ma łamanie wiersza, lista dostaje klasę `dla-kogo-wiersze` i liczbę rzędów `--rzedy` (numer, tytuł, wiersze najdłuższego opisu); od 1024 px n-ty wiersz każdej pozycji leży w jednym rzędzie (pozycja i jej treść — subgrid przez wszystkie rzędy). Bez łamań wiersza i poniżej 1024 px — układ bez zmian.

## Edytor

- **[fh5myv]** Wiersze opisów nie są wyrównywane — opis pozycji to jedno pole tekstowe.

## Przykład

```html
<!-- wp:feuer/dla-kogo {"tytul":"Kiedy skorzystasz ze wsparcia BHP na start?","lead":"Szkolenie musi zostać zrealizowane <strong>przed rozpoczęciem pracy</strong>.","podpis":"Szkolenie należy zorganizować dla:"} -->
<!-- wp:feuer/dla-kogo-pozycja {"opis":"wszystkich osób nowo zatrudnionych na podstawie umowy o pracę"} /-->
<!-- wp:feuer/dla-kogo-pozycja {"opis":"pracowników zaczynających pracę na nowym stanowisku"} /-->
<!-- wp:feuer/dla-kogo-pozycja {"opis":"uczniów i studentów odbywających praktyki"} /-->
<!-- wp:feuer/dla-kogo-pozycja {"opis":"osób dopuszczonych do pracy po dłuższej przerwie"} /-->
<!-- /wp:feuer/dla-kogo -->
```
