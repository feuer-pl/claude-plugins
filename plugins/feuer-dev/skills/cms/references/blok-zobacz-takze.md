# feuer/zobacz-takze

„Zobacz także" — sekcja na tle wyróżnionym z nagłówkiem i karuzelą 1–10 produktów (szkoleń i usług): powiązania produktu albo wybór ręczny. Typ: D ([bloki.md](bloki.md), „Typy bloków"). Powiązane produkty: [produkt.md](produkt.md), [m2vmwe], [srrv3u]; wybór ręczny: [bloki.md](bloki.md), „Źródła pozycji"; karuzela: [bloki.md](bloki.md), „Karuzele".

## Gdzie

- **[6t63eh]** Samodzielna sekcja w treści produktów i stron, w dowolnej liczbie na stronie; bez bloków potomnych.

## Pola

| ID | Pole | Atrybut | Rodzaj | Dozwolone | Limit | Wymagane / domyślne |
|---|---|---|---|---|---|---|
| **[dt3qat]** | Nagłówek (H2, w całości ExtraBold) | `tytul` | tekst z łamaniem wiersza, w miejscu | „Akcent w nagłówkach — bez akcentu" ([bloki.md](bloki.md), [bmw7u4]); na froncie `wp_kses_post` | bez limitu | pusty (po usunięciu znaczników) — „Inni klienci wybierali także" (i18n; w edytorze jako wartość pola) |
| **[8gk8xa]** | Pozycje (źródło) — tylko na stronie produktu | `zrodlo` | wybór „Pozycje" (panel „Ustawienia"): „Powiązania produktu" (podpowiedź „Z sekcji „Powiązane produkty" w danych produktu (pod treścią)."), „Wybór ręczny" | `powiazania`, `reczny` | — | `powiazania`; na innych stronach zawsze wybór ręczny, bez wyboru źródła |
| **[7fj2yj]** | Produkty (wybór ręczny) | `produkty` (lista ID) | panel wyboru ręcznego | produkty (szkolenia i usługi) | 10 | pusta |
| **[aj9p5c]** | Szerokość tła | `szerokoscTla` | panel „Ustawienia" — wspólne ustawienie szerokości tła: css.md, [k34pyh] | `1440`, `1920` | — | `1440` |

## Dane

- **[drt5r8]** Powiązania — z `_feuer_powiazane` bieżącego wpisu, tylko na stronie produktu przy źródle „Powiązania produktu" (kontekst `postId`, `postType`); pierwsze 10 dostępnych w kolejności listy. Lista ręczna przycinana do pierwszych 10 ID. Pozycje — wyłącznie opublikowane produkty (typ `produkt`); nieopublikowane i usunięte pomijane na froncie i w podglądzie, limit 10 liczy pozycje dostępne.
- **[ucc8t4]** Pozycja — jeden link do strony produktu (inna niż karta produktu — [strony-zbiorcze.md](strony-zbiorcze.md), [kejzfv]): zdjęcie (obrazek wyróżniający, brak — stan „bez zdjęcia", [strony-zbiorcze.md](strony-zbiorcze.md), [3dh7tn]; dekoracyjne, leniwe) z tagiem (badge z `_feuer_tag`, bez tagu gdy pusty — [strony-zbiorcze.md](strony-zbiorcze.md), [vjmjws]), nazwa na karcie ([produkt.md](produkt.md), [hh6g67]) i strzałka ↗.
- **[q682bd]** Skład: sekcja na tle wyróżnionym (`tlo-wyroznione`) — H2, karuzela (`div.swiper` z `ul.swiper-wrapper`) i pojemnik na kreski `.wskazniki-karuzeli`. Brak pozycji (po filtrach) — zachowanie wg [bloki.md](bloki.md), [szj5f5].

## Edytor

- **[g58uyp]** Nagłówek — lustrzany markup z edycją w miejscu; pozycje — HTML z `render.php`; karuzela w stanie startowym: rząd od pierwszej pozycji, kreski jak liczba zatrzaśnięć (od 1024 px — n − 2 przy więcej niż 3 pozycjach, przy 3 i mniej bez kresek; próg odczytywany z okna kanwy, także w podglądzie mobile), pierwsza aktywna ([bloki.md](bloki.md), [8jw4ud]); pełna lista wyboru ręcznego — w panelu. Linki pozycji w podglądzie — [bloki.md](bloki.md), [ap7hv3].
- **[zggfvd]** Przy powiązaniach z ponad 10 dostępnymi panel pokazuje ostrzeżenie „Pokazane pierwsze 10 z N powiązanych produktów." (N — liczba dostępnych powiązań).
- **[p3496h]** Brak pozycji — nagłówek z komunikatem: przy powiązaniach „Brak powiązanych produktów do pokazania — dodaj je w danych produktu („Powiązane produkty") albo wybierz produkty w ustawieniach bloku. Na stronie blok się nie wyświetla.", przy wyborze ręcznym „Brak produktów do pokazania — wybierz produkty w ustawieniach bloku. Na stronie blok się nie wyświetla."; podczas wczytywania danych albo po błędzie — sam nagłówek.

## Przykład

```html
<!-- wp:feuer/zobacz-takze /-->

<!-- wp:feuer/zobacz-takze {"tytul":"Sprawdź też \u003cspan class=\u0022akcent-marki\u0022\u003einne\u003c/span\u003e szkolenia","zrodlo":"reczny","produkty":[146,150,152]} /-->
```
