# feuer/aktualnosci

„Aktualności" — sekcja z czterema najnowszymi artykułami (pierwszy jako duża karta ze zdjęciem, trzy tekstowe), nagłówkiem i linkiem do strony z wpisami. Typ: D ([bloki.md](bloki.md), „Typy bloków"); źródło pozycji: [bloki.md](bloki.md), [fejddw]; flaga „Nie pokazuj na listach artykułów": [artykuly.md](artykuly.md), [jwnmvv].

## Gdzie

- **[kpw8kf]** Samodzielna sekcja pełnej szerokości w treści stron, poza paletą treści redakcyjnej; w projekcie ostatnia sekcja strony głównej. Ograniczenia typu wpisu nie ma.

## Pola

| ID | Pole | Atrybut | Rodzaj | Dozwolone | Limit | Wymagane / domyślne |
|---|---|---|---|---|---|---|
| **[bkg4kd]** | Nagłówek (H2) | `tytul` | tekst z łamaniem wiersza (Shift+Enter) | „Akcent w nagłówkach" ([bloki.md](bloki.md), [s56shy]) | — | pusty — tekst domyślny z projektu ([bloki.md](bloki.md), [w7etph]): „16 lat na rynku... i wciąż się u nas dzieje" (z akcentami; w każdym języku jego tłumaczenie) |
| **[j8zngm]** | Tekst linku | `etykietaLinku` | tekst z łamaniem wiersza, w miejscu | „Krótki tekst" ([bloki.md](bloki.md), [nmwmdu], [taeeq4]) | — | pusty (także same łamania i spacje) — „Sprawdź więcej newsów" przez i18n |
| **[cry8up]** | Szerokość tła | `szerokoscTla` | panel „Ustawienia" — wspólne ustawienie szerokości tła: css.md, [k34pyh] | `1440`, `1920` | — | `1440` |

## Dane

- **[kr2hhn]** Pozycje: 4 najnowsze opublikowane wpisy (`post`) wg daty publikacji malejąco, przy tej samej dacie wyższe ID pierwsze (front i edytor); wpisy przyklejone bez pierwszeństwa; bez filtra kategorii i ustawień w bloku. Pierwszy wpis — duża karta ze zdjęciem, pozostałe — karty tekstowe w liście; mniej wpisów — tyle kart, ile jest (pierwsza zawsze duża); bez wpisów — zachowanie wg [bloki.md](bloki.md), [szj5f5].
- **[z6wmdu]** Karta: cała jest linkiem do wpisu (↗ — dekoracyjna ikona `i-strzalka-skos`, nie osobny link); hover — tytuł w kolorze marki. Pola z natywnych pól wpisu: data publikacji („j F Y" przez kontekst i18n „format daty w bloku Aktualności", `<time datetime>` Y-m-d), tytuł (H3), opis = zajawka (pusta — bez opisu), zdjęcie dużej karty = obrazek wyróżniający (alt pusty, leniwe; brak — zapasowy wizual jak w szablonie artykułu).
- **[mrapge]** Link prowadzi do strony z wpisami (Ustawienia → Czytanie — Baza wiedzy; w innym języku jej tłumaczenie); bez ustawionej strony z wpisami link się nie wyświetla.

## Edytor

- **[2mt5nn]** Nagłówek i link — lustrzany markup z edycją w miejscu; pozycje — `ServerSideRender` z parametrem `feuer_pozycje` (`render.php` zwraca samą listę); linki w podglądzie — [bloki.md](bloki.md), [ap7hv3].
- **[mw3tj5]** Brak wpisów do pokazania — nagłówek z komunikatem „Brak opublikowanych wpisów — na stronie blok się nie wyświetla." (inaczej bloku nie da się zaznaczyć).

## Przykład

```html
<!-- wp:feuer/aktualnosci /-->

<!-- wp:feuer/aktualnosci {"tytul":"Co nowego \u003cspan class=\u0022akcent\u0022\u003ew Feuer\u003c/span\u003e","etykietaLinku":"Wszystkie wpisy"} /-->
```
