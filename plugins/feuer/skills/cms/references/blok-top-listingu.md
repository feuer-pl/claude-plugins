# feuer/top-listingu

„Top visual listingu" — sekcja otwierająca stron zbiorczych oferty: ciemne zdjęcie na całą szerokość, okruszki, H1 i lead; na stronie kategorii — dane termu. Typ: T, w trybie kategorii D ([bloki.md](bloki.md), „Typy bloków"). Tryb kategorii: [strony-zbiorcze.md](strony-zbiorcze.md), [n7rpch]; okruszki na zdjęciu: [nawigacja.md](nawigacja.md), [xmubhb]; pole wyszukiwarki: [strony-zbiorcze.md](strony-zbiorcze.md), [gdpzwn].

## Gdzie

- **[qe8tj6]** Strona „Oferta" i strony lądowania (`page`) — wstawiany przez redaktora; strona kategorii — w sekcji `kategoria-<slug-termu>` (zablokowany); najwyżej jeden na stronę (`supports.multiple: false`).

## Pola

Pola poza trybem kategorii (w trybie kategorii ignorowane — dane z termu):

| ID | Pole | Atrybut | Rodzaj | Dozwolone | Limit | Wymagane / domyślne |
|---|---|---|---|---|---|---|
| **[3k4v4r]** | Zdjęcie | `zdjecie` (ID) | medium — toolbar: „Wybierz zdjęcie" / „Zmień zdjęcie" | obrazy z biblioteki mediów | — | obowiązkowe — niewybrane albo usunięte: obraz zastępczy (front i edytor); `loading="eager"` i `fetchpriority="high"` ([media.md](media.md), [s4ae2p]) |
| **[qakenc]** | H1 | `tytul` | tekst jednowierszowy, w miejscu | bez formatów (na froncie bez znaczników) | bez limitu | pusty (po usunięciu znaczników i spacji) — tytuł strony; w edytorze tytuł wpisu jako podpowiedź |
| **[guhf6y]** | Lead | `lead` | tekst z łamaniem wiersza, w miejscu, podpowiedź „Lead…" | pogrubienie (na froncie `strong`, `br`) | bez limitu | opcjonalne — pusty się nie wyświetla |

## Dane

- **[rhe2w7]** Tryb kategorii rozpoznawany na froncie po `is_tax('oferta')`, w edytorze — po slugu edytowanej sekcji `kategoria-…` (bez sprawdzania, czy term istnieje). Poza nim blok czyta kontekst wpisu (`postId`, `postType`) — wpis z kontekstu (brak — bieżący) daje domyślny H1.
- **[vwbdjd]** Markup: `section.top-listingu.tlo-ciemne` — `.scena-zdjecie` (zdjęcie; bez zdjęcia `.bez-zdjecia`) i `.kontener` (`.sciezka`, `h1.top-tytul`, `p.top-lead`, pole wyszukiwarki jako ostatni element).

## Edytor

- **[p57yp7]** Lustrzany markup z `edit()`, HTML na froncie wyłącznie z `render.php` (`save` = `null`). W sekcji kategorii — dane termu bez edycji i bez wyboru zdjęcia; poza nią edycja w miejscu i wybór zdjęcia w toolbarze. Ścieżka okruszków z `render.php` dla edytowanej strony, nieaktywna.
- **[d6pkyc]** Pusty lead widoczny (pole z podpowiedzią) tylko przy zaznaczonym bloku.

## Wielojęzyczność

- **[jh6sr5]** W trybie kategorii nazwa i opis z termu `oferta` (taksonomia nietłumaczona — [wielojezycznosc.md](wielojezycznosc.md), [7n3mcs]); reszta wg [bloki.md](bloki.md), [49nkuy].

## Przykład

```html
<!-- wp:feuer/top-listingu {"zdjecie":123,"tytul":"Oferta Feuer","lead":"Szkolenia, doradztwo i obsługa BHP dla firm — od obowiązkowych szkoleń po systemy zarządzania bezpieczeństwem."} /-->
```
