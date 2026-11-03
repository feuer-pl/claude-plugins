# feuer/top-kontentowy

„Top visual kontentowy" — sekcja otwierająca stron kontentowych, stron filarów, stron branży, strony Bazy wiedzy i strony wyników wyszukiwania: zdjęcie (albo film), na nim link „Wstecz" (poniżej 1024 px; okruszki desktopu — rząd ramy nad blokiem: [nawigacja.md](nawigacja.md), [xmubhb]), etykieta, H1 = tytuł wpisu i karta z treścią redakcyjną. Typ: T ([bloki.md](bloki.md), „Typy bloków"). Wzorzec „Strona kontentowa": [wzorce-stron.md](wzorce-stron.md), [3pz3w9]; sekcja branży: [sekcje.md](sekcje.md), [8h54zx]; strona Bazy wiedzy (H1): [baza-wiedzy.md](baza-wiedzy.md); strona wyników wyszukiwania: wyszukiwarka.md, „Strona wyników"; film: [bloki.md](bloki.md), „Film zamiast zdjęcia".

## Gdzie

- **[epr4zu]** Pierwsza pozycja, zablokowany (`lock` — bez przesuwania i usuwania): wzorzec „Strona kontentowa" (strony kontentowe i filarów, `page`), zestaw startowy sekcji branży `branza-<slug-termu>`, sekcje `baza-wiedzy` i `wyniki-wyszukiwania`. Poza wstawiaczem, jeden na stronę (`multiple: false`) — ręcznie wstawić się go nie da.
- **[ctfyb5]** Osobny komponent, nie odmiana hero.

## Pola

| ID | Pole | Atrybut | Rodzaj | Dozwolone | Limit | Wymagane / domyślne |
|---|---|---|---|---|---|---|
| **[uc7qh3]** | Etykieta kategorii | `etykieta` | tekst jednowierszowy, w miejscu | bez formatów | 45 | obowiązkowe |
| **[664zac]** | H1 — tytuł wpisu (wiązanie `useEntityProp`, nie kopia; zmiana tekstu zmienia tytuł wpisu — SEO, okruszki) | tytuł wpisu + `tytulAkcent` | tekst jednowierszowy, w miejscu; podpowiedź „Tytuł strony…" | akcent — słowo większe (`feuer/tytul-duzy`, `span.tytul-duzy`), kolor marki, kursywa, podkreślenie; bez linków ([bloki.md](bloki.md), [nwcsbu]) | — | tytuł wpisu; w sekcji `baza-wiedzy` — tytuł strony z wpisami, w sekcji branży — tytuł sekcji; w sekcji `wyniki-wyszukiwania` — na froncie „Wyniki wyszukiwania: <hasło>" ([jpbbbd]) |
| **[27t9xv]** | Karta | bloki wewnętrzne | strefa treści — typografia treści redakcyjnej (A40, `.tresc`) | paleta treści redakcyjnej ([paleta-tresci.md](paleta-tresci.md), [8psccg]) | — | obowiązkowe; po wstawieniu jeden pusty akapit z podpowiedzią `<wprowadź dane>` |
| **[n38er8]** | Zdjęcie | obrazek wyróżniający wpisu (bez pola w bloku; wybór w panelu wpisu) | medium | obrazy | — | obowiązkowe — brak albo usunięty: obraz zastępczy; `loading="eager"` i `fetchpriority="high"` ([media.md](media.md), [s4ae2p]); jedno zdjęcie dla desktopu i mobile |
| **[87bepv]** | Film, Film mobile | `film`, `filmMobile` | medium — toolbar ([bloki.md](bloki.md), [hcje6t]) | MP4 | — | opcjonalne — zamiast zdjęcia |
| **[gg6yex]** | Szerokość tła | `szerokoscTla` | panel „Ustawienia" — wspólne ustawienie szerokości tła: css.md, [k34pyh] | `1440`, `1920` | — | `1920` |

## Warianty

- **[vwd7jk]** Wariant akcentowy H1: co najmniej jedno słowo z akcentem (`span.tytul-duzy`) — `h1.tytul-akcent` (krótkie tytuły); bez formatowania — zwykły tytuł bez słów innej wielkości. Formatowanie zapisuje się w `tytulAkcent` (pusty, gdy w H1 nie ma znaczników) i wyświetla, dopóki jego tekst (bez znaczników, z rozkodowanymi encjami) jest równy tytułowi wpisu — tytuł zmieniony poza blokiem to zwykły tytuł (ta sama logika w edytorze).
- **[jpbbbd]** Sekcja `wyniki-wyszukiwania` (strona wyników — wyszukiwarka.md, [qy2afr]): na froncie H1 „Wyniki wyszukiwania: <hasło>" (puste hasło — „Wyniki wyszukiwania"), formularz wyszukiwania serwisu (wyszukiwarka.md, [j3da32]) w dwóch kopiach (widoczna jedna) — od 1024 px na zdjęciu pod H1 (odstęp `--odstep-8`), szerokość 5 kolumn siatki; poniżej 1024 px pod zdjęciem, 24 niżej, na całą szerokość kontenera; karta niewyświetlana (w edytorze sekcji zostaje), zdjęcie na wysokość treści — pod formularzem 70 jak nad etykietą, poniżej 1024 px 24 pod H1. W edytorze sekcji H1 = tytuł sekcji.
- **[cv54wq]** Sekcja `baza-wiedzy` od 1024 px: zdjęcie na wysokość treści — pod H1 70 jak nad etykietą, karta nachodzi na zdjęcie jak w pozostałych sekcjach (152); poniżej 1024 px — jak w pozostałych sekcjach.
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
