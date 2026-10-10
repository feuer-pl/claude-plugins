# feuer/baza-wiedzy

„Strona Bazy wiedzy" — cały `<main>` strony z wpisami (Baza wiedzy, `/baza-wiedzy/`) w szablonie motywu `home.html`. Typ: szablonowy ([bloki.md](bloki.md), „Typy bloków"). Strona Bazy wiedzy (szablon, treść z sekcji, lista artykułów): [baza-wiedzy.md](baza-wiedzy.md); sekcja `baza-wiedzy`: [sekcje.md](sekcje.md).

## Gdzie

- **[5wjt39]** Bez atrybutów; poza wstawiaczem ([bloki.md](bloki.md), [89q53x]), bez zapisu jako blok wielokrotnego użytku ([bloki.md](bloki.md), [ecp7bd]).
- **[4wtujz]** `<main>` z klasą `baza-wiedzy`; klasa treści strony — [strony.md](strony.md), [uzqjqk].

## Dane

- **[xcfhp5]** Sekcja `baza-wiedzy` ([sekcje.md](sekcje.md), [rrzbuy]) — dodawana w Sekcje → Dodaj (slug `baza-wiedzy`) albo poleceniem WP-CLI; treść początkowa: Top visual kontentowy i Lista artykułów (oba zablokowane: bez przesuwania i usuwania), Sekcja kontaktowa:

```bash
wp eval '$z = serialize_block_attributes( array( "lock" => array( "move" => true, "remove" => true ) ) ); wp_insert_post( wp_slash( array( "post_type" => "sekcja", "post_status" => "publish", "post_title" => "Baza wiedzy", "post_name" => "baza-wiedzy", "post_content" => "<!-- wp:feuer/top-kontentowy $z -->\n<!-- wp:paragraph -->\n<p></p>\n<!-- /wp:paragraph -->\n<!-- /wp:feuer/top-kontentowy -->\n\n<!-- wp:feuer/lista-artykulow $z /-->\n\n<!-- wp:feuer/sekcja-kontaktowa /-->" ) ) );'
```

## Edytor

- **[69vqx5]** Znacznik miejsca w edytorze witryny ([bloki.md](bloki.md), [nv2eze]): „Strona Bazy wiedzy — treść sekcji Bazy wiedzy".

## Przykład

```html
<!-- wp:feuer/baza-wiedzy /-->
```
