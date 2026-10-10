# feuer/kafle-kategorii

„Kafle kategorii" — siatka kafli kategorii oferty, każdy prowadzi do strony kategorii. Typ: D ([bloki.md](bloki.md), „Typy bloków"); kafel kategorii (wspólny ze stroną kategorii): [strony-zbiorcze.md](strony-zbiorcze.md), [47wr84]; źródła pozycji: [bloki.md](bloki.md), „Źródła pozycji".

## Gdzie

- **[gxp463]** Samodzielna sekcja w treści stron, poza paletą treści redakcyjnej; w projekcie strona „Oferta" pod Top visualem listingu; na stronie dowolnie wiele bloków.

## Pola

| ID | Pole | Atrybut | Rodzaj | Dozwolone | Limit | Wymagane / domyślne |
|---|---|---|---|---|---|---|
| **[wekqr3]** | Kafle (źródło) | `zrodlo` | przełącznik „Kafle" (panel „Ustawienia") | „Podkategorie wskazanej kategorii" (`dzieci`), „Wybór ręczny" (`reczny`) | — | `dzieci` |
| **[vferrw]** | Kategoria (źródło „dzieci") | `rodzic` (ID termu) | lista „Kategoria" z podpowiedzią „Kafle w kolejności utworzenia…" | „Kategorie najwyższego poziomu" (0) i kategorie oferty z wcięciami | — | 0 — po wstawieniu kategorie najwyższego poziomu |
| **[yq7kfy]** | Kategorie (wybór ręczny) | `kategorie` (lista ID termów) | pole „Dodaj kategorię" i lista wybranych (kolejność kafli) | kategorie oferty bez już wybranych | — | pusta; kategoria usunięta z taksonomii — w panelu „Kategoria N (usunięta)" |

## Dane

- **[ccvafg]** Źródło „dzieci": podkategorie kategorii `rodzic` (0 — najwyższy poziom), kolejność jak w menu ([taksonomie.md](taksonomie.md), [xktvsv]); pomijana kategoria bez produktów widocznych w listingu — w niej i w podkategoriach ([strony-zbiorcze.md](strony-zbiorcze.md), [g62a6w]).
- **[amvmk9]** Wybór ręczny: kategorie z listy w jej kolejności, każda także bez produktów; term nieistniejący w taksonomii `oferta` — pominięty.

## Edytor

- **[u86bhu]** Brak kafli — w ich miejscu komunikat: wybór ręczny — „Brak kategorii do pokazania — wybierz kategorie w ustawieniach bloku. Na stronie blok się nie wyświetla.", źródło „podkategorie" — „Wskazana kategoria nie ma podkategorii z produktami — wybierz inną w ustawieniach bloku. Na stronie blok się nie wyświetla."

## Wielojęzyczność

- **[7g8xdg]** Nazwa, zdjęcie i ikona kafla — z termu `oferta`, wspólnego dla języków (taksonomia nietłumaczona — [wielojezycznosc.md](wielojezycznosc.md), [7n3mcs]).

## Przykład

```html
<!-- wp:feuer/kafle-kategorii /-->

<!-- wp:feuer/kafle-kategorii {"rodzic":16} /-->

<!-- wp:feuer/kafle-kategorii {"zrodlo":"reczny","kategorie":[24,13,2]} /-->
```
