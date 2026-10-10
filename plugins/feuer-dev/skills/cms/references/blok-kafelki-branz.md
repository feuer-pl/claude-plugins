# feuer/kafelki-branz

„Kafelki branż" — sekcja z nagłówkiem, kafelkiem na każdą branżę i kaflem „Inna branża?" otwierającym layer kontaktu. Typ: D ([bloki.md](bloki.md), „Typy bloków"); źródło pozycji: [bloki.md](bloki.md), [fejddw]; lista i kolejność branż: [taksonomie.md](taksonomie.md), [4c6qy5].

## Gdzie

- **[yq2xj4]** Samodzielna sekcja pełnej szerokości w treści stron, poza paletą treści redakcyjnej; w projekcie strona główna, między karuzelami szkoleń. Ograniczenia typu wpisu nie ma.

## Pola

| ID | Pole | Atrybut | Rodzaj | Dozwolone | Limit | Wymagane / domyślne |
|---|---|---|---|---|---|---|
| **[kdf42p]** | Nagłówek (H2) | `tytul` | tekst z łamaniem wiersza | „Akcent w nagłówkach" ([bloki.md](bloki.md), [s56shy]) | — | pusty — tekst domyślny z projektu przez i18n (wersja desktopowa): „Każda branża ma swoje wyzwania w BHP. / My mamy ludzi od każdej branży." (druga linia z akcentem) — na froncie i w edytorze; nie zapisywany w atrybucie |
| **[jv8ueq]** | Tekst kafla „Inna branża?" | `inna` | tekst z łamaniem wiersza | bez formatów | — | pusty — „Inna branża? / Sprawdź co jeszcze!" przez i18n; nie zapisywany w atrybucie |

- **[dyzsux]** Bez ustawień w panelu bloku — kafelki branż pochodzą z danych.

## Dane

- **[grhhjj]** Kafelek na każdy term `branza` (także bez produktów), redaktor nie ustawia listy; cały kafelek jest linkiem do strony branży (`/branza/<slug-termu>/`): ikona z meta termu (`_feuer_ikona`; obowiązkowa — brak: obraz zastępczy; dekoracyjna, leniwa), nazwa termu (`h3`), podpis = opis termu (czysty tekst; obowiązkowy — pusty: `<wprowadź dane>`), strzałka.
- **[7xfqc4]** Kafel „Inna branża?" — ostatni w siatce: ciemny przycisk (`<button data-layer="layer-kontakt">`, moduł `feuer-layer`) z ikoną zaszytą w stylu i samym tekstem z pola `inna` — bez tekstu pomocniczego, linku „Skontaktuj się z nami" i pola linku; na desktopie zawsze na szerokość dwóch kafelków.
- **[94y9nm]** Hover każdego kafla (także „Inna branża?"): tło czerwone, tekst i ikona białe, strzałka ↗ zmienia się w →; czerwony kafelek z projektu to stan hover — blok nie ma odmiany wyróżnionej.
- **[k6zrjp]** Brak branż — blok wyświetla się z nagłówkiem i samym kaflem „Inna branża?", bez osobnej obsługi.

## Edytor

- **[4yspsq]** Kafel „Inna branża?" w edytorze to `div` ([bloki.md](bloki.md), [pufx5c]); linki kafelków branż w podglądzie — [bloki.md](bloki.md), [ap7hv3].

## Wielojęzyczność

- **[d9mz3k]** Branże wspólne dla języków — taksonomia nietłumaczona ([wielojezycznosc.md](wielojezycznosc.md), [7n3mcs]).

## Przykład

```html
<!-- wp:feuer/kafelki-branz /-->

<!-- wp:feuer/kafelki-branz {"tytul":"Szkolimy <span class=\"akcent\">każdą branżę</span>","inna":"Nie ma Twojej branży?"} /-->
```
