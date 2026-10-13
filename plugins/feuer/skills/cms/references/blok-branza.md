# feuer/branza

„Strona branży" — cały `<main>` strony branży `/branza/<slug-termu>/` w szablonie motywu `taxonomy-branza.html`. Typ: szablonowy ([bloki.md](bloki.md), „Typy bloków"). Szablon, treść z sekcji branży i listing: [strony-zbiorcze.md](strony-zbiorcze.md), „Strona branży"; sekcja `branza-<slug termu>` i jej zestaw startowy: [sekcje.md](sekcje.md), „Sekcje kategorii i branż".

## Gdzie

- **[sn8jut]** Bez atrybutów; poza wstawiaczem ([bloki.md](bloki.md), [89q53x]), bez zapisu jako blok wielokrotnego użytku ([bloki.md](bloki.md), [ecp7bd]).

## Dane

- **[r7n8qt]** Blok renderuje się wyłącznie na stronie termu taksonomii `branza`; w każdym innym kontekście nic nie wypisuje.
- **[dfq6n2]** Sekcje branż dla istniejących termów (termy z sekcją są pomijane) — polecenie WP-CLI:

```bash
wp eval 'foreach ( get_terms( array( "taxonomy" => "branza", "hide_empty" => false ) ) as $t ) feuer_sekcja_branzy_utworz( $t->term_id );'
```

## Edytor

- **[ves5z2]** Znacznik miejsca w edytorze witryny ([bloki.md](bloki.md), [nv2eze]): „Strona branży — treść sekcji bieżącej branży": treść pochodzi z sekcji oglądanej branży.

## Przykład

```html
<!-- wp:feuer/branza /-->
```
