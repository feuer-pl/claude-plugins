# feuer/terminy

„Terminy" — sekcja z nagłówkiem, leadem i rzędem kart najbliższych aktualnych terminów szkoleń; przy bieżącym szkoleniu bez terminów — stan pusty z sekcji `terminy-brak`. Typ: D ([bloki.md](bloki.md), „Typy bloków"). Źródło kart i brak terminów: [bloki.md](bloki.md), [g93eyy], [xrqdvx]; aktualne terminy: [produkt.md](produkt.md), [d566w4]; teksty stanu pustego: [feuer/terminy-brak](blok-terminy-brak.md); prewypełnienie layeru: formularz-kontaktu.md, [zfmtfn], [7x4m9c]; „Zamów" karty szkolenia gotowego do zapisu — formularz zapisu: formularz-zapisu.md, [8bhh5a].

## Gdzie

- **[wmat39]** Samodzielna sekcja w treści stron i produktów (we wzorcu „Szkolenie"), poza paletą treści redakcyjnej.
- **[avsguw]** Osobny komponent, nie wariant rodziny „nagłówek + rząd pozycji" (Dla kogo, Proces współpracy) — karty z danych terminów, nie redagowane; jedna struktura karty (data, tytuł, opis, akcja), bez odmiany „artykułowej".

## Pola

| ID | Pole | Atrybut | Rodzaj | Dozwolone | Limit | Wymagane / domyślne |
|---|---|---|---|---|---|---|
| **[kuk964]** | Nagłówek (H2) | `tytul` | tekst z łamaniem wiersza, w miejscu | „Akcent w nagłówkach" ([bloki.md](bloki.md), [s56shy]) | — | pusty — „Terminy otwartych szkoleń" (i18n) |
| **[nc3jfr]** | Lead | `lead` | tekst z łamaniem wiersza, w miejscu; na froncie łamanie usuwane | pogrubienie | — | opcjonalne — pusty się nie wyświetla |
| **[8zw62y]** | Tekst przycisku kart — jedno pole dla wszystkich kart ([bloki.md](bloki.md), [5tj3aw]) | `przycisk` | tekst jednowierszowy, w miejscu | bez formatów | — | pusty — „Zamów" |
| **[dz7a5s]** | Liczba kart | `limit` | toolbar bloku ([bloki.md](bloki.md), [4dtarj]) | wartości z [4dtarj]; inna wartość daje 4 | — | 4; mniej terminów niż limit — rząd niepełny, karty o szerokości z limitu |
| **[jw8sf6]** | Źródło terminów | `zrodlo`, `oferta` (ID termu) | jedna lista w panelu „Ustawienia": „Bieżące szkolenie" (tylko na stronie produktu), „Wszystkie szkolenia" (0), kategorie oferty z wcięciami ([bloki.md](bloki.md), [ck9xys]) | — | — | na stronie produktu — bieżące szkolenie (`zrodlo` puste albo `biezace`), gdzie indziej — wszystkie szkolenia; poza stroną produktu zawsze oferta |

## Dane

- **[xh5u8t]** Bieżące szkolenie z kontekstu bloku (`postId`, `postType`) — warunek: strona produktu (bez sprawdzania rodzaju); terminy liczone tylko dla rodzaju „szkolenie" — produkt innego rodzaju ze źródłem „bieżące" pokazuje stan pusty.
- **[bahnhs]** Karta: data — dzień (dwie cyfry) i miesiąc w mianowniku wielką literą z rokiem („Luty 2026"; i18n, `<time>` z datą terminu); tytuł — przy bieżącym szkoleniu forma terminu (słownik, i18n; termin bez formy — pusty wiersz podsiatki), przy ofercie nazwa szkolenia na karcie, a forma pogrubiona pierwszym wierszem opisu (bez formy — sam opis); opis terminu — zwykły tekst z łamaniami, bez HTML; przycisk `button.link-akcji` z `aria-label` = tekst przycisku, nazwa szkolenia i data.
- **[vqnsvw]** Stan pusty (bieżące szkolenie bez aktualnych terminów): zamiast kart nagłówek, lead i przycisk A41 z pierwszego bloku `feuer/terminy-brak` opublikowanej sekcji `terminy-brak` (jedna dla wszystkich języków — [sekcje.md](sekcje.md), [8bcbuy]); brak sekcji albo bloku — Terminy bez kart w ogóle się nie wyświetlają.

## Edytor

- **[acvbxw]** Stan pusty — HTML z JSON `render.php` (pole `pusty`), jak na froncie, bez edycji w bloku (teksty — w sekcji `terminy-brak`).
- **[g7x4qn]** Wybrane źródło bez aktualnych terminów (poza stanem pustym) — w miejscu kart komunikat „Brak aktualnych terminów w wybranym źródle — na stronie blok się nie wyświetla."

## Wielojęzyczność

- **[3pac9z]** Daty i forma terminu wspólne dla języków, opis terminu — z tłumaczenia szkolenia ([produkt.md](produkt.md), [pyhqcb]); reszta wg [bloki.md](bloki.md), [49nkuy].

## Przykład

```html
<!-- wp:feuer/terminy {"tytul":"Terminy otwartych szkoleń","lead":"Otwarte szkolenia online w formie webinarów prowadzimy średnio raz w miesiącu. Sprawdź najbliższe sesje."} /-->

<!-- wp:feuer/terminy {"tytul":"Terminy szkoleń podstawowych","lead":"Najbliższe terminy szkoleń podstawowych.","przycisk":"Zapisz się","limit":3,"zrodlo":"oferta","oferta":11} /-->
```
