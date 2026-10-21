# feuer/karta-opisu-produktu-pozycja

„Pozycja" — etap bloku [feuer/karta-opisu-produktu](blok-karta-opisu-produktu.md): nadtytuł, tytuł i treść redakcyjna. Typ: T ([bloki.md](bloki.md), „Typy bloków").

## Gdzie

- **[7wm7qp]** Wyłącznie wewnątrz `feuer/karta-opisu-produktu` ([bloki.md](bloki.md), [raemfr]); bez blokady i zapisu jako blok wielokrotnego użytku ([bloki.md](bloki.md), [ecp7bd]).

## Pola

| ID | Pole | Atrybut | Rodzaj | Dozwolone | Limit | Wymagane / domyślne |
|---|---|---|---|---|---|---|
| **[anu6vd]** | Nadtytuł (np. „Etap I", na stronach produktów „1." … „4.") | `nadtytul` | tekst jednowierszowy | bez formatów | bez limitu | opcjonalne — pusty (po usunięciu znaczników i spacji) się nie wyświetla |
| **[qevafg]** | Tytuł | `tytul` | tekst z łamaniem wiersza (na froncie tylko `br`) | bez formatów | 35 | obowiązkowe |
| **[gzrcmd]** | Treść (panel zakładki albo kolumna; typografia treści redakcyjnej A40, `.tresc`) | bloki wewnętrzne | strefa treści, swobodna (`templateLock: false`) | paleta treści redakcyjnej ([paleta-tresci.md](paleta-tresci.md), [8psccg]) i blok Terminy szkoleń otwartych ([feuer/terminy-otwarte](blok-terminy-otwarte.md)); nagłówki h3–h4 ([2qrdcd]) | bez limitu | opcjonalne — pusta treść: pusty panel albo kolumna, bez znacznika |

## Dane

- **[angtjq]** Front (render serwera; treść zapisana jako bloki wewnętrzne): „Zakładki" — przycisk `button.program-zakladka` (`data-zakladka`, `aria-expanded="false"`, `aria-controls` = unikalne `program-panel-N`; nadtytuł i tytuł w `span`) i panel; „Kolumny" — `li.program-kolumna`: nadtytuł, tytuł `h3`, treść w `div.tresc`.
- **[3p4tbz]** Linki w treści etapu to zwykła treść redakcyjna — render przekazuje treść bez przetwarzania (bez rozwiązywania na tłumaczenie).

## Edytor

- **[2qrdcd]** Nagłówki w treści etapu — poziomy 3–4 (h2 zarezerwowany dla nagłówka sekcji): lista poziomów zawężona; nagłówek wstawiony, wklejony albo przeniesiony z innym poziomem dostaje najbliższy dozwolony (korekta poza historią zmian); przekształcenie w „Nagłówek 2" w menu bloku ukryte, dopóki zaznaczony blok leży w treści etapu (wstrzyknięty styl `.editor-block-list-item-h2` — warianty poziomów są globalne dla typu bloku).
- **[d9zrgj]** Pusty nadtytuł (podpowiedź „Nadtytuł (opcjonalny)…") widoczny tylko przy zaznaczonym etapie.

## Przykład

```html
<!-- wp:feuer/karta-opisu-produktu-pozycja {"nadtytul":"Etap I","tytul":"Planowanie i projektowanie"} -->
<!-- wp:paragraph -->
<p>Na etapie budowy lub adaptacji obiektu BHP to moment, w którym błędy kosztują najwięcej.</p>
<!-- /wp:paragraph -->
<!-- /wp:feuer/karta-opisu-produktu-pozycja -->
```
