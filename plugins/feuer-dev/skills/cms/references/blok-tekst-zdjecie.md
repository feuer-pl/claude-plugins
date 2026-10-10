# feuer/tekst-zdjecie

„Sekcja tekst+zdjęcie" — jeden rząd: zdjęcie i kolumna tekstu obok siebie, po 6 kolumn siatki. Typ: T ([bloki.md](bloki.md), „Typy bloków").

## Gdzie

- **[3aw65e]** Samodzielna sekcja pełnej szerokości w treści stron i produktów, poza paletą treści redakcyjnej.
- **[rp84bz]** Jeden blok = jeden rząd, bez bloków potomnych; kolejne rzędy — kolejne bloki jeden pod drugim, bez limitu. Bez nagłówka sekcji — nagłówek, jeśli potrzebny, jest treścią kolumny tekstu.

## Pola

| ID | Pole | Atrybut | Rodzaj | Dozwolone | Limit | Wymagane / domyślne |
|---|---|---|---|---|---|---|
| **[t85cje]** | Zdjęcie | `zdjecie` (ID) | medium — toolbar: „Wybierz zdjęcie" / „Zmień zdjęcie" (`MediaReplaceFlow`); alt z biblioteki mediów, bez atrybutu `alt` w bloku | obrazy z biblioteki mediów | — | obowiązkowe — niewybrane albo usunięte: obraz zastępczy ([bloki.md](bloki.md), [wdhnxv]) |
| **[ve2ajx]** | Strona zdjęcia | `stronaZdjecia` | wybór w toolbarze: „Zdjęcie z lewej", „Zdjęcie z prawej" — działa tylko od 1024 px (w DOM zdjęcie zawsze przed tekstem, niżej — nad tekstem) | `lewa`, `prawa` | — | `lewa` |
| **[zszz2m]** | Treść (kolumna tekstu; typografia A40, `.tresc`) | bloki wewnętrzne | strefa treści, swobodna (`templateLock: false`) | paleta treści redakcyjnej bez ograniczeń ([paleta-tresci.md](paleta-tresci.md), [8psccg], [bfkh35]) | — | opcjonalne — pusta kolumna zostaje pusta, bez znacznika; po wstawieniu jeden pusty akapit (bez oznaczania zmiany) |
| **[25ykqp]** | Odstęp u góry / u dołu | `bezGornegoOdstepu`, `bezDolnegoOdstepu` | przełączniki „Wyłącz odstęp u góry", „Wyłącz odstęp u dołu" (panel „Ustawienia") | — | — | odstępy włączone; wyłączony — padding 0 po tej stronie na każdej szerokości |

## Dane

- **[6fd3nk]** Zdjęcie przez `feuer_zdjecie()`, `loading="lazy"` ([media.md](media.md), [tewya3]), `sizes`: 36.625rem (586 px) od 1024 px, 100vw poniżej.

## Przykład

```html
<!-- wp:feuer/tekst-zdjecie {"zdjecie":123} -->
<!-- wp:paragraph -->
<p><strong>Jesteśmy zespołem ekspertów specjalizujących się w doradztwie i szkoleniach BHP. Od 2010 roku pomagamy firmom w Polsce budować systemy BHP, które działają na co dzień - nie tylko przy kontroli.</strong></p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul class="wp-block-list"><!-- wp:list-item -->
<li>Mamy stały zespół ekspercki wspierany przez szeroką bazę trenerów i konsultantów z doświadczeniem branżowym.</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Obsługujemy firmy polskie i zagraniczne z różnych branż – od energetyki po logistykę, od chemii po budownictwo.</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:buttons -->
<div class="wp-block-buttons"><!-- wp:button {"className":"is-style-drugorzedny"} -->
<div class="wp-block-button is-style-drugorzedny"><a class="wp-block-button__link wp-element-button" href="https://feuer.pl/o-firmie/">Dowiedz się więcej</a></div>
<!-- /wp:button --></div>
<!-- /wp:buttons -->
<!-- /wp:feuer/tekst-zdjecie -->
```
