# feuer/przycisk-artykulu

„Przycisk artykułu" — sekcja z jednym przyciskiem do powiązanego artykułu bieżącego produktu. Typ: D ([bloki.md](bloki.md), „Typy bloków"). Powiązany artykuł: [produkt.md](produkt.md), [zyzxke], [v2qktg]; wzorce produktu: [wzorce-stron.md](wzorce-stron.md), [m9behp].

## Gdzie

- **[3zw55h]** Samodzielna sekcja w treści, we wstawiaczu, bez ograniczenia typu wpisu i liczby na stronie; we wzorcach produktu i w treści produktów — bezpośrednio przed Belką informacyjną w odmianie „Zdjęcie i karta".

## Pola

| ID | Pole | Atrybut | Rodzaj | Dozwolone | Limit | Wymagane / domyślne |
|---|---|---|---|---|---|---|
| **[qjgsj2]** | Tekst przycisku | `przycisk` | tekst jednowierszowy, w miejscu | bez formatów | — | pusty — „Dowiedz się więcej w artykule" (i18n) |

## Dane

- **[sgsjjv]** Adres — powiązany artykuł bieżącego wpisu (`_feuer_artykul`, kontekst `postId`; adres w języku strony: [wielojezycznosc.md](wielojezycznosc.md), [b8tb5u]); pola linku w bloku nie ma.
- **[rykr3h]** Artykuł nieustawiony, nieopublikowany albo usunięty (także wpis bez pola — strona, artykuł) — na froncie blok się nie renderuje.

## Edytor

- **[hp6tb6]** Lustrzany markup z edycją tekstu w miejscu (tekst w elemencie `span` — [bloki.md](bloki.md), [pufx5c]); bez opublikowanego artykułu pod przyciskiem komunikat „Produkt nie ma opublikowanego powiązanego artykułu — wskaż go w danych produktu („Powiązany artykuł"). Na stronie przycisk się nie wyświetla." — czy artykuł jest, liczy `render.php` (`feuer_dane`: [bloki.md](bloki.md), [s598n9]).

## Przykład

```html
<!-- wp:feuer/przycisk-artykulu /-->

<!-- wp:feuer/przycisk-artykulu {"przycisk":"Przeczytaj artykuł o szkoleniu wstępnym"} /-->
```
