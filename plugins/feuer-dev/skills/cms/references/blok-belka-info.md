# feuer/belka-info

„Belka informacyjna" — sekcja ze zdjęciem (albo filmem), nagłówkiem z akcentem i jednym przyciskiem, w dwóch odmianach. Typ: T ([bloki.md](bloki.md), „Typy bloków"). Film zamiast zdjęcia: [bloki.md](bloki.md), „Film zamiast zdjęcia"; prewypełnienie layeru kontaktu: formularz-kontaktu.md, [4xqbx5].

## Gdzie

- **[cbyyc3]** Samodzielna sekcja pełnej szerokości w treści stron i produktów, poza paletą treści redakcyjnej; ograniczenia typu wpisu nie ma.

## Pola

| ID | Pole | Atrybut | Rodzaj | Dozwolone | Limit | Wymagane / domyślne |
|---|---|---|---|---|---|---|
| **[qn69dd]** | Odmiana | `odmiana` | wybór w toolbarze bloku: „Tekst i zdjęcie" (1), „Zdjęcie i karta" (2) | 1, 2 — każda wartość inna niż 2 to odmiana 1; obie odmiany w każdym wpisie | — | 1 |
| **[nknu94]** | Nagłówek (H2) | `tytul` | tekst z łamaniem wiersza (Shift+Enter) | „Akcent w nagłówkach" ([bloki.md](bloki.md), [s56shy]) — w obu odmianach, kolor marki wybiera redaktor | — | obowiązkowe |
| **[2fkzpc]** | Akapit (tylko odmiana 1) | `tekst` | tekst z łamaniem wiersza, podpowiedź „Akapit…" | pogrubienie | — | opcjonalne — pusty się nie wyświetla; w odmianie 2 zostaje w atrybucie, niewyświetlany |
| **[2skqv8]** | Przycisk (atom A41 ze strzałką) | `przycisk`: `etykieta`, `url`, `id`, `zamowienie` | etykieta — tekst jednowierszowy w miejscu; cel — toolbar: „Link przycisku" (kontrolka linku: [bloki.md](bloki.md), [wawuac], [a4xc8h]; wybór linku zeruje `zamowienie`) albo „Zamówienie produktu" (`zamowienie: true` — layer kontaktu z prewypełnieniem, bez adresu; adres linku zostaje w atrybucie, niewyświetlany) | etykieta bez formatów | — | obowiązkowe — bez etykiety: `<wprowadź dane>`; z etykietą bez celu (bez linku albo zamówienie poza stroną produktu): `<wprowadź link>` w miejscu tekstu (front; w edytorze tekst zostaje do edycji); znaczniki bez strzałki i celu |
| **[39u63z]** | Zdjęcie (dekoracyjne, alt pusty) | `zdjecie` (ID) | medium — toolbar: „Wybierz zdjęcie" / „Zmień zdjęcie" | obrazy z biblioteki mediów | — | obowiązkowe — niewybrane albo usunięte: obraz zastępczy ([bloki.md](bloki.md), [wdhnxv]) |
| **[uh68kk]** | Film, Film mobile | `film`, `filmMobile` | medium — toolbar: „Film", „Film mobile", „Resetuj" ([bloki.md](bloki.md), [hcje6t]) | MP4 | — | opcjonalne — zamiast zdjęcia; plik mobile poniżej 1024 px |
| **[f8vb7e]** | Szerokość tła | `szerokoscTla` | panel „Ustawienia" — wspólne ustawienie szerokości tła: css.md, [k34pyh] | `1440`, `1920` | — | `1440` |

## Warianty

- **[p39mka]** Jeden blok z przełącznikiem odmiany, bez odmian jasnej i ciemnej (obie na białym tle). Odmiana 1 „Tekst i zdjęcie": nagłówek, akapit, przycisk; zdjęcie z prawej wystaje w następną sekcję — pas tła wyróżnionego u dołu (`.belka-info-pas`) jest częścią bloku. Odmiana 2 „Zdjęcie i karta": zdjęcie z lewej, karta z obrysem marki z nagłówkiem i przyciskiem, bez akapitu i pasa.

## Dane

- **[ujmd7b]** Blok czyta kontekst bieżącego wpisu (`postId`, `postType`) — cel „zamówienie produktu": produkt = bieżący wpis typu `produkt`; render — `<button>` wyzwalacz layeru kontaktu, a przy szkoleniu gotowym do zapisu — formularza zapisu (formularz-zapisu.md, [3zuhr3]). Przycisk „Zamówienie produktu" w toolbarze tylko na stronie produktu (`postType` = `produkt`) albo przy bloku, który już ma `zamowienie` (przeniesiony z produktu — wtedy wyłącznie do przełączenia na link); poza produktem cel to link (np. do strony „Kontakt").
- **[kenag5]** Zdjęcie w rozmiarze `full` z `srcset`; `loading="lazy"` ([media.md](media.md), [tewya3]); `sizes` wg kadru: 704 px od 1024 px, 100vw poniżej.

## Przykład

```html
<!-- wp:feuer/belka-info {"tytul":"Zarządzanie przez\u003cbr\u003e\u003cspan class=\u0022akcent\u0022\u003e\u003cspan class=\u0022akcent-marki\u0022\u003ebezpieczeństwo.\u003c/span\u003e\u003c/span\u003e","tekst":"Dobre procedury od startu to fundament \u003cstrong\u003ezarządzania przez bezpieczeństwo\u003c/strong\u003e.","przycisk":{"etykieta":"Poznaj nasze podejście","url":"https://feuer.pl/o-firmie/","id":6},"zdjecie":123} /-->

<!-- wp:feuer/belka-info {"odmiana":2,"tytul":"Nie musisz znać polskich przepisów BHP.\u003cbr\u003e\u003cspan class=\u0022akcent\u0022\u003eMusisz znać kogoś, kto je zna.\u003c/span\u003e","przycisk":{"etykieta":"Porozmawiajmy o współpracy","url":"https://feuer.pl/kontakt/","id":9},"zdjecie":124} /-->
```
