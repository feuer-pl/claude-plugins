# feuer/lista-artykulow

„Lista artykułów" — lista artykułów w grupach wg kategorii oferty, ze źródłem wybieranym w bloku; w sekcji `baza-wiedzy` — lista strony Bazy wiedzy. Typ: D ([bloki.md](bloki.md), „Typy bloków"). Źródła, grupy, pozycje, tagi, tryb Bazy wiedzy, wyszukiwarka: [baza-wiedzy.md](baza-wiedzy.md), „Lista artykułów"; wybór ręczny: [bloki.md](bloki.md), „Źródła pozycji".

## Gdzie

- **[pkyqm9]** Redaktor wstawia blok w treść stron, w dowolnej liczbie na stronie; w sekcji `baza-wiedzy` — zablokowany. Bez zapisu jako blok wielokrotnego użytku ([bloki.md](bloki.md), [ecp7bd]); bez pól tekstowych.

## Pola

| ID | Pole | Atrybut | Rodzaj | Dozwolone | Limit | Wymagane / domyślne |
|---|---|---|---|---|---|---|
| **[t8jn3h]** | Artykuły (źródło) | `zrodlo` | wybór „Artykuły" w panelu „Ustawienia"; podpowiedź: źródła automatyczne — „Artykuły wskazane polem „Powiązany artykuł" przez produkty źródła, w grupach wg kategorii; bez artykułów z oznaczeniem „Nie pokazuj na listach artykułów"."; wybór ręczny — „Kolejność listy = kolejność wyboru; bez nagłówków grup." | „Wszystkie artykuły" (`wszystkie`), „Kategoria oferty" (`oferta`), „Branża" (`branza`), „TOP 20" (`top-20`), „Miesiące" (`miesiace`), „Wybór ręczny" (`reczny`) | — | `wszystkie` (także atrybut pusty) |
| **[zmfx85]** | Kategoria oferty | `oferta` (ID termu) | lista „Kategoria oferty": „— wybierz —" i drzewo kategorii z wcięciami ([bloki.md](bloki.md), [ck9xys]); podpowiedź o kolejności grup | kategorie oferty | — | 0 — lista pusta |
| **[v8bgms]** | Branża | `branza` (ID termu) | lista „Branża": „— wybierz —" i wszystkie branże; podpowiedź „Wyłącznie produkty z tą branżą przypisaną wprost; pozycje bez tagów branż." | branże | — | 0 — lista pusta |
| **[ejprst]** | Miesiące | `miesiace` (slugi oznaczeń) | pola wyboru dwunastu miesięcy (słownik oznaczeń bez „TOP 20", z renderu) | miesiące | — | pusta — lista pusta |
| **[bnhbjx]** | Artykuły (wybór ręczny) | `artykuly` (ID w kolejności redaktora) | panel wyboru „Artykuły" / „Dodaj artykuł" | wpisy `post` | — | pusta |

## Dane

- **[xq95v3]** Pusta lista (źródło bez wskazanego termu albo miesiąca, wybór ręczny bez opublikowanych artykułów, brak grup) — zachowanie wg [bloki.md](bloki.md), [szj5f5].

## Edytor

- **[n28tjt]** Podgląd — `ServerSideRender` (POST) z parametrem `feuer_pozycje` (render zwraca samo wnętrze sekcji); linki w podglądzie — [bloki.md](bloki.md), [ap7hv3]; dodanie artykułu i zmiana źródła odświeżają podgląd bez zapisu; pusta lista — komunikat „Brak artykułów do pokazania — zmień źródło w ustawieniach bloku. Na stronie blok się nie wyświetla.".
- **[g839bu]** W trybie Bazy wiedzy panel pokazuje tylko informację „Źródło: wszystkie artykuły — stałe na stronie Bazy wiedzy." — bez wyboru źródła.

## Wielojęzyczność

- **[bv34dn]** Artykuł z pola produktu — przez `feuer_wpis_w_biezacym_jezyku()`; „Pozostałe" — przez i18n; reszta wg [bloki.md](bloki.md), [49nkuy].

## Przykład

```html
<!-- wp:feuer/lista-artykulow {"lock":{"move":true,"remove":true}} /-->

<!-- wp:feuer/lista-artykulow {"zrodlo":"oferta","oferta":11} /-->
```
