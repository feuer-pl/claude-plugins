# feuer/dwie-kolumny-kolumna

„Kolumna" — jedna z dwóch kolumn bloku [feuer/dwie-kolumny](blok-dwie-kolumny.md). Typ: T ([bloki.md](bloki.md), „Typy bloków").

## Gdzie

- **[9eebzn]** Wyłącznie wewnątrz `feuer/dwie-kolumny` ([bloki.md](bloki.md), [raemfr]), poza wstawiaczem; redaktor jej nie wstawia ani nie usuwa; bez blokady i zapisu jako blok wielokrotnego użytku ([bloki.md](bloki.md), [ecp7bd]).

## Pola

| ID | Pole | Atrybut | Rodzaj | Dozwolone | Limit | Wymagane / domyślne |
|---|---|---|---|---|---|---|
| **[ewvhgt]** | Zawartość kolumny | bloki wewnętrzne | strefa treści | `core/image`, `core/paragraph`, `core/list` — w dowolnej kolejności i liczbie | — | nowa kolumna: jeden pusty akapit |

## Przykład

```html
<!-- wp:feuer/dwie-kolumny-kolumna -->
<!-- wp:paragraph -->
<p>Tekst kolumny.</p>
<!-- /wp:paragraph -->
<!-- /wp:feuer/dwie-kolumny-kolumna -->
```
