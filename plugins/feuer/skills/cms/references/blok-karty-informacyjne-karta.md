# feuer/karty-informacyjne-karta

„Karta informacyjna" — karta bloku [feuer/karty-informacyjne](blok-karty-informacyjne.md): tytuł, tekst, w odmianie hero opcjonalny link. Typ: T ([bloki.md](bloki.md), „Typy bloków").

## Gdzie

- **[kcjt2v]** Wyłącznie wewnątrz `feuer/karty-informacyjne` ([bloki.md](bloki.md), [raemfr]); bez blokady i zapisu jako blok wielokrotnego użytku ([bloki.md](bloki.md), [ecp7bd]); bez bloków wewnętrznych (`save` = `null`).

## Pola

| ID | Pole | Atrybut | Rodzaj | Dozwolone | Limit | Wymagane / domyślne |
|---|---|---|---|---|---|---|
| **[a27pq5]** | Tytuł | `tytul` | tekst z łamaniem wiersza (Enter), podpowiedź „Tytuł karty…" | bez formatów (na froncie tylko `br`) | bez limitu | opcjonalne — pusty się nie wyświetla, bez znacznika |
| **[cwqjja]** | Tekst | `tekst` | jeden akapit bez łamania wiersza (`disableLineBreaks`), podpowiedź „Tekst karty…" | pogrubienie (na froncie tylko `strong`) | bez limitu | opcjonalne — pusty się nie wyświetla, bez znacznika |
| **[hsqpg8]** | Link (tylko odmiana hero) | `link`: `url`, `id` | „Link karty" w toolbarze karty (widoczny tylko w hero) — okno z kontrolką linku | wpis serwisu albo adres | — | opcjonalne |

## Dane

- **[hh47yj]** Front: `li.swiper-slide.karta-informacyjna` — slajd karuzeli rodzica z polem karty: z linkiem (hero) — `a.karta-informacyjna-pole` z `href`; bez linku — `div.karta-informacyjna-pole`; hover i efekt naciśnięcia — [README rodzica](blok-karty-informacyjne.md), [p4uqab].
- **[jx84nv]** Poza odmianą hero link jest ignorowany na froncie, nawet gdy atrybut jest wypełniony ([README rodzica](blok-karty-informacyjne.md), [p4uqab]); po wyłączeniu hero linki zostają w atrybutach.

## Przykład

```html
<!-- wp:feuer/karty-informacyjne-karta {"tytul":"16 lat<br>na rynku pracy","tekst":"Obsługujemy firmy polskie i zagraniczne od 2010 roku."} /-->
<!-- wp:feuer/karty-informacyjne-karta {"tytul":"Zbuduj fundamenty BHP w firmie","link":{"url":"https://feuer.pl/o-firmie/fundamenty-bezpieczenstwa/","id":743}} /-->
```
