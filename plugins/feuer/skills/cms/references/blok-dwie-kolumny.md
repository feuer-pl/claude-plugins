# feuer/dwie-kolumny

„Dwie kolumny" — dwie kolumny w treści, w każdej zdjęcie, akapit albo lista. Typ: T ([bloki.md](bloki.md), „Typy bloków"); element palety treści redakcyjnej ([paleta-tresci.md](paleta-tresci.md), [q7ddhc]). Kolumna: [feuer/dwie-kolumny-kolumna](blok-dwie-kolumny-kolumna.md).

## Pola

| ID | Pole | Atrybut | Rodzaj | Dozwolone | Limit | Wymagane / domyślne |
|---|---|---|---|---|---|---|
| **[kawe36]** | Kolumny | bloki wewnętrzne | dokładnie dwie kolumny; szablon zablokowany (`templateLock: 'all'`) — bez dodawania, usuwania i przestawiania | wyłącznie `feuer/dwie-kolumny-kolumna` | 2 | dwie kolumny |

## Warianty

- **[grude7]** Odmiany z projektu (zdjęcie + tekst, zdjęcie + lista, lista + lista) wynikają ze składu kolumn — bez przełącznika w bloku.

## Przykład

```html
<!-- wp:feuer/dwie-kolumny -->
<!-- wp:feuer/dwie-kolumny-kolumna -->
<!-- wp:image {"id":123} --><figure class="wp-block-image"><img src="…" alt="" class="wp-image-123"/></figure><!-- /wp:image -->
<!-- /wp:feuer/dwie-kolumny-kolumna -->
<!-- wp:feuer/dwie-kolumny-kolumna -->
<!-- wp:paragraph --><p>Tekst kolumny.</p><!-- /wp:paragraph -->
<!-- /wp:feuer/dwie-kolumny-kolumna -->
<!-- /wp:feuer/dwie-kolumny -->
```
