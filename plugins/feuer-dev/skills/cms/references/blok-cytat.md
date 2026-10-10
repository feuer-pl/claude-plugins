# feuer/cytat

„Opinia klienta" — duży cudzysłów (zaszyty), cytat, podpis i opcjonalny przycisk. Typ: T ([bloki.md](bloki.md), „Typy bloków"); element palety treści redakcyjnej ([paleta-tresci.md](paleta-tresci.md), [3dw525]). „Cytat" we wstawiaczu to cytat blokowy `core/quote` ([paleta-tresci.md](paleta-tresci.md), [zawnfx]); wzorce produktu Opinii klienta nie zawierają ([wzorce-stron.md](wzorce-stron.md), [u3zw36]).

## Gdzie

- **[kyf54t]** W strefach treści z paletą i bezpośrednio w treści stron i produktów, między sekcjami. Tryb wynika z miejsca, bez ustawienia: w strefie treści (m.in. artykuł, etap i kolumna Programu, kolumna Sekcji tekst+zdjęcie) — blok treści redakcyjnej (A40); na najwyższym poziomie treści strony albo produktu — samodzielna sekcja w białym pasie. W artykułach (`post`) zawsze blok treści — reguła sekcji nie obejmuje wpisów.

## Pola

| ID | Pole | Atrybut | Rodzaj | Dozwolone | Limit | Wymagane / domyślne |
|---|---|---|---|---|---|---|
| **[z8ztmt]** | Cytat | `cytat` | tekst z łamaniem wiersza | pogrubienie, kursywa, link, podkreślenie, przekreślenie (formaty palety bez koloru marki); na froncie `wp_kses_post` | bez limitu | obowiązkowe |
| **[ga4u7f]** | Podpis — jeden tekst: imię, rolę, pogrubienie i podział na wiersze wpisuje redaktor | `podpis` | tekst z łamaniem wiersza | jak Cytat | bez limitu | obowiązkowe |
| **[rffk9p]** | Przycisk (drugorzędny ze strzałką A41, wygląd zaszyty) | `przycisk`: `etykieta`, `url`, `id` | etykieta — tekst jednowierszowy w miejscu (na froncie czysty tekst); adres — „Link przycisku" w toolbarze (podświetlony przy ustawionym adresie; kontrolka linku: [bloki.md](bloki.md), [wawuac]) | bez formatów | — | opcjonalne — pusty tekst (po `trim`): brak przycisku, także po wstawieniu; tekst bez adresu: `<wprowadź link>` zamiast tekstu, bez strzałki i `href` |

## Dane

- **[9bxeme]** Markup: `figure.cytat` → `blockquote` → `p` (`span.cytat-znak` — cudzysłów `ikony/cudzyslow.svg`, ozdobny, `aria-hidden`, bez edycji — + cytat), `figcaption`, `a.przycisk.przycisk-drugorzedny`.

## Edytor

- **[q87gry]** Pusty przycisk z podpowiedzią „Przycisk (opcjonalny)…" widoczny tylko przy zaznaczonym bloku; po wpisaniu tekstu — zawsze; strzałka przycisku — [bloki.md](bloki.md), [jtnzgj].

## Przykład

```html
<!-- wp:feuer/cytat {"cytat":"Nie wiedziałem, że szkolenie BHP może być tak ciekawe, dopóki nie poznałem Feuer","podpis":"<strong>Filip Makowiecki</strong> CEO w Fajrant Design&amp;Research","przycisk":{"etykieta":"Przeczytaj o współpracy","url":"https://feuer.pl/…/","id":42}} /-->
```
