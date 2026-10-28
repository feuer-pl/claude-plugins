# feuer/top-kontentowy

„Top visual kontentowy" — sekcja otwierająca stron kontentowych, stron filarów, stron branży i strony Bazy wiedzy: zdjęcie (albo film), na nim link „Wstecz" (poniżej 1024 px; okruszki desktopu — rząd ramy nad blokiem: [nawigacja.md](nawigacja.md), [xmubhb]), etykieta, H1 = tytuł wpisu i karta z treścią redakcyjną. Typ: T ([bloki.md](bloki.md), „Typy bloków"). Wzorzec „Strona kontentowa": [wzorce-stron.md](wzorce-stron.md), [3pz3w9]; sekcja branży: [sekcje.md](sekcje.md), [8h54zx]; strona Bazy wiedzy (H1, pole wyszukiwania): [baza-wiedzy.md](baza-wiedzy.md); film: [bloki.md](bloki.md), „Film zamiast zdjęcia".

## Gdzie

- **[epr4zu]** Pierwsza pozycja, zablokowany (`lock` — bez przesuwania i usuwania): wzorzec „Strona kontentowa" (strony kontentowe i filarów, `page`), zestaw startowy sekcji branży `branza-<slug-termu>`, sekcja `baza-wiedzy`. Poza wstawiaczem, jeden na stronę (`multiple: false`) — ręcznie wstawić się go nie da.
- **[ctfyb5]** Osobny komponent, nie odmiana hero.

## Pola

| ID | Pole | Atrybut | Rodzaj | Dozwolone | Limit | Wymagane / domyślne |
|---|---|---|---|---|---|---|
| **[uc7qh3]** | Etykieta kategorii | `etykieta` | tekst jednowierszowy, w miejscu | bez formatów | 45 | obowiązkowe |
| **[664zac]** | H1 — tytuł wpisu (wiązanie `useEntityProp`, nie kopia; zmiana tekstu zmienia tytuł wpisu — SEO, okruszki) | tytuł wpisu + `tytulAkcent` | tekst jednowierszowy, w miejscu; podpowiedź „Tytuł strony…" | akcent — słowo większe (`feuer/tytul-duzy`, `span.tytul-duzy`), kolor marki, kursywa, podkreślenie; bez linków ([bloki.md](bloki.md), [nwcsbu]) | — | tytuł wpisu; w sekcji `baza-wiedzy` — tytuł strony z wpisami, w sekcji branży — tytuł sekcji |
| **[27t9xv]** | Karta | bloki wewnętrzne | strefa treści — typografia treści redakcyjnej (A40, `.tresc`) | paleta treści redakcyjnej ([paleta-tresci.md](paleta-tresci.md), [8psccg]) | — | obowiązkowe; po wstawieniu jeden pusty akapit z podpowiedzią `<wprowadź dane>` |
| **[n38er8]** | Zdjęcie | obrazek wyróżniający wpisu (bez pola w bloku; wybór w panelu wpisu) | medium | obrazy | — | obowiązkowe — brak albo usunięty: obraz zastępczy; `loading="eager"` i `fetchpriority="high"` ([media.md](media.md), [s4ae2p]); jedno zdjęcie dla desktopu i mobile |
| **[87bepv]** | Film, Film mobile | `film`, `filmMobile` | medium — toolbar ([bloki.md](bloki.md), [hcje6t]) | MP4 | — | opcjonalne — zamiast zdjęcia |
| **[gg6yex]** | Szerokość zdjęcia w tle | `szerokoscTla` | panel „Ustawienia" — wspólne ustawienie bloków ze zdjęciem-tłem: css.md, [k34pyh] | `1440`, `1920` | — | `1440` |

## Warianty

- **[vwd7jk]** Wariant akcentowy H1: co najmniej jedno słowo z akcentem (`span.tytul-duzy`) — `h1.tytul-akcent` (krótkie tytuły); bez formatowania — zwykły tytuł bez słów innej wielkości. Formatowanie zapisuje się w `tytulAkcent` (pusty, gdy w H1 nie ma znaczników) i wyświetla, dopóki jego tekst (bez znaczników, z rozkodowanymi encjami) jest równy tytułowi wpisu — tytuł zmieniony poza blokiem to zwykły tytuł (ta sama logika w edytorze).
- **[hxyjwk]** Jedna albo dwie kolumny karty wynikają ze składu treści, bez przełącznika: bloki palety bezpośrednio w karcie — jedna kolumna (np. lead i przyciski na stronach filarów), blok „Dwie kolumny" w karcie — kolumny 5 : 7.

## Dane

- **[dczw2q]** Karta bez treści (także same puste akapity) — na froncie akapit ze znacznikiem `<wprowadź dane>`; samo zdjęcie (`<img>` bez tekstu) jest treścią.

## Edytor

- **[n6rfzf]** Na stronie (wpisie) z blokiem pole tytułu edytora jest ukryte — tytuł wpisuje się wyłącznie w H1 bloku; wpisy bez bloku mają pole bez zmian.
- **[kct7f3]** Karta bez bloków — pusty akapit ze znacznikiem wg [bloki.md](bloki.md), [ywafc8]; pusty blok nie oznacza wpisu jako zmienionego.

## Przykład

```html
<!-- wp:feuer/top-kontentowy {"etykieta":"O firmie","tytulAkcent":"\u003cspan class=\u0022tytul-duzy\u0022\u003eFeuer\u003c/span\u003e — zarządzanie przez \u003cspan class=\u0022tytul-duzy\u0022\u003ebezpieczeństwo\u003c/span\u003e","lock":{"move":true,"remove":true}} -->
<!-- wp:heading -->
<h2 class="wp-block-heading">Kim jesteśmy?</h2>
<!-- /wp:heading -->

<!-- wp:feuer/dwie-kolumny -->
<!-- wp:feuer/dwie-kolumny-kolumna -->
<!-- wp:paragraph {"className":"is-style-wstep"} -->
<p class="is-style-wstep">Jesteśmy zespołem ekspertów specjalizujących się w doradztwie i szkoleniach BHP.</p>
<!-- /wp:paragraph -->
<!-- /wp:feuer/dwie-kolumny-kolumna -->

<!-- wp:feuer/dwie-kolumny-kolumna -->
<!-- wp:list -->
<ul class="wp-block-list"><!-- wp:list-item -->
<li>Mamy stały zespół ekspercki.</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->
<!-- /wp:feuer/dwie-kolumny-kolumna -->
<!-- /wp:feuer/dwie-kolumny -->
<!-- /wp:feuer/top-kontentowy -->
```
