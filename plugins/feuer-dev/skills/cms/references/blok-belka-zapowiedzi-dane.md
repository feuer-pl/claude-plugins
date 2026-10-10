# feuer/belka-zapowiedzi-dane

„Belka zapowiedzi — treść" — pola belki zapowiedzi i przełącznik „Pokazuj belkę", w treści sekcji `belka-zapowiedzi`; w treść stron i wpisów wstawia się [feuer/belka-zapowiedzi](blok-belka-zapowiedzi.md). Typ: T ([bloki.md](bloki.md), „Typy bloków"). Sekcja i blokada struktury: [sekcje.md](sekcje.md), [yyq58q].

## Gdzie

- **[vuskm5]** Wyłącznie w sekcji `belka-zapowiedzi`: poza wstawiaczem, raz w treści (`multiple: false`), bez zapisu jako blok wielokrotnego użytku ([bloki.md](bloki.md), [ecp7bd]).

## Pola

| ID | Pole | Atrybut | Rodzaj | Dozwolone | Limit | Wymagane / domyślne |
|---|---|---|---|---|---|---|
| **[dv7j3s]** | Pokazuj belkę | `pokazuj` | przełącznik (panel boczny „Ustawienia") | — | — | włączone; wyłączone — belka nie renderuje się nigdzie, dane i wstawione bloki zostają |
| **[kkk7vk]** | Chip (atom A46) | `chip` | tekst jednowierszowy, w miejscu | bez formatów (na froncie czysty tekst) | — | opcjonalne — pusty się nie wyświetla |
| **[byq8u7]** | Zdanie zapowiedzi (H2, w całości ExtraBold) | `tytul` | tekst z łamaniem wiersza, w miejscu | „Akcent w nagłówkach — bez akcentu" ([bloki.md](bloki.md), [bmw7u4]) | — | obowiązkowe |
| **[f7qmrc]** | Link (link akcji A43 ze strzałką) | `link`: `etykieta`, `url`, `id` | etykieta — tekst jednowierszowy w miejscu; adres — przycisk „Link" w toolbarze (kontrolka linku: [bloki.md](bloki.md), [wawuac], [a4xc8h]) | bez formatów | — | obowiązkowe — bez etykiety: `<wprowadź dane>`, z etykietą bez adresu: `<wprowadź link>` (oba bez strzałki i `href`) |
| **[p2ukva]** | Znak graficzny (dekoracyjny, alt pusty) | `znak` (ID obrazu) | medium — toolbar „Wybierz znak" / „Zmień znak", „Resetuj" (po wyborze) | SVG (zalecany), PNG z przezroczystym tłem; proporcje 16:9, znak do krawędzi kadru; raster min. 344 × 194 px, zalecany 512 × 288 px — bez walidacji | — | znak domyślny `ikony/znak-belki.svg` — gdy niewybrany albo usunięty z biblioteki |

## Dane

- **[utzzts]** Znak jeden dla belki (pole bloku w sekcji) — wspólny dla wszystkich miejsc wstawienia, bez wymiany per wstawienie.
- **[b844fm]** Obraz znaku bez `loading="lazy"` — na telefonie belka leży w pierwszym ekranie strony głównej.
- **[areyxy]** Treść początkowa sekcji = przykład niżej ([sekcje.md](sekcje.md), [rrzbuy]); np. WP-CLI `wp post create - --post_type=sekcja --post_name=belka-zapowiedzi --post_status=publish` z treścią na wejściu.

## Edytor

- **[uwvake]** Belka wyłączona — nad podglądem ostrzeżenie „Belka wyłączona — nie wyświetla się nigdzie."

## Wielojęzyczność

- **[8hz8be]** Teksty pól, znak i link — jedna sekcja dla wszystkich języków (typ `sekcja` nietłumaczony: [sekcje.md](sekcje.md), [8bcbuy]); link wskazany wpisem — [bloki.md](bloki.md), [a4xc8h].

## Przykład

```html
<!-- wp:feuer/belka-zapowiedzi-dane {"chip":"Szkolenie online","tytul":"19 maja. Webinar Nowe przepisy dot. ergonomii pracy biurowej.","link":{"etykieta":"Zapisz się już teraz","url":"https://feuer.pl/kontakt/","id":9}} /-->
```
