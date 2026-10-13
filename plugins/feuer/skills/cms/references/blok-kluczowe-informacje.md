# feuer/kluczowe-informacje

„Kluczowe informacje" — sekcja na tle wyróżnionym z nagłówkiem i białą kartą: wariant „wstęp" (lead i treść redakcyjna) albo „tabela z danych" szkolenia (tabela albo zakładki grup). Typ: T (wstęp) / D (tabela z danych) ([bloki.md](bloki.md), „Typy bloków"). Dane tabeli: [produkt.md](produkt.md), [y6rd8s]; zakładki i akordeon: [bloki.md](bloki.md), „Zakładki i akordeon".

## Gdzie

- **[mvh9j4]** Samodzielna sekcja w treści stron i produktów, w dowolnej liczbie na stronie; wariant „tabela z danych" — tylko produkt rodzaju „szkolenie" (wzorzec „Szkolenie" zawiera blok w tym wariancie), „wstęp" — także strony.

## Pola

| ID | Pole | Atrybut | Rodzaj | Dozwolone | Limit | Wymagane / domyślne |
|---|---|---|---|---|---|---|
| **[b9zatx]** | Wariant | `wariant` | toolbar: „Wstęp" (zawsze), „Tabela z danych" (tylko na stronie szkolenia) | `wstep`, `tabela` | — | bez wartości domyślnej — nieustawiony: na stronie szkolenia tabela, gdzie indziej wstęp (edytor zapisuje go po wczytaniu danych, poza podglądem) |
| **[48r8c9]** | Nagłówek (H2, w całości ExtraBold) | `tytul` | tekst z łamaniem wiersza, w miejscu | „Akcent w nagłówkach — bez akcentu" ([bloki.md](bloki.md), [bmw7u4]) | bez limitu | pusty (po usunięciu znaczników) — „Kluczowe informacje o szkoleniu" (i18n), także na stronach |
| **[r5jweu]** | Lead (wstęp, z lewej) | `lead` | tekst z łamaniem wiersza, w miejscu | „Akcent w nagłówkach" ([bloki.md](bloki.md), [s56shy]) | bez limitu | obowiązkowe |
| **[k2wphx]** | Treść wstępu (z prawej; typografia A40, `.tresc`) | bloki wewnętrzne | strefa treści | paleta treści redakcyjnej ([paleta-tresci.md](paleta-tresci.md), [8psccg]) | bez limitu | obowiązkowe — bez tekstu i zdjęć (także sam pusty akapit): `<wprowadź dane>`; przy wariancie „tabela" zostaje w bloku, niewyświetlana |

## Dane

- **[94de6b]** Tabela z danych: grupy wierszy z meta `_feuer_kluczowe` bieżącego wpisu, wyłącznie gdy to `produkt` rodzaju „szkolenie" (kontekst `postId`, `postType`). Jedna grupa — karta z tabelą definicji (nazwa grupy się nie wyświetla), kilka grup — zakładki z nazwami grup, pierwsza aktywna (poniżej 1024 px akordeon).
- **[td8aw3]** Wartość wiersza — HTML z edytora klasycznego (akapity z pustych wierszy — `wpautop`; listy, formaty inline palety), każda tak samo, w `.tresc` (A40); etykieta i nazwa grupy — tekst bez formatów.
- **[f97nyw]** Wariant „tabela" bez żadnego wiersza albo poza stroną szkolenia (np. po zmianie rodzaju) — zachowanie wg [bloki.md](bloki.md), [szj5f5]. Dane niekompletne — znacznik `<wprowadź dane>` w miejscu braku: pusta etykieta, pusta wartość, grupa bez nazwy przy kilku grupach, grupa bez wierszy (jeden wiersz ze znacznikami w etykiecie i wartości).

## Edytor

- **[n2m9a5]** Wstęp: lustrzany markup z edycją w miejscu; treść bez bloków — pusty akapit ze znacznikiem wg [bloki.md](bloki.md), [ywafc8] (poza historią cofania).
- **[r7hq8d]** Tabela: HTML z `render.php` w stanie startowym zakładek jak na froncie, wczytywany od nowa po zapisie metaboksów; linki wartości w podglądzie — [bloki.md](bloki.md), [ap7hv3]. Brak danych — nagłówek z komunikatem: na szkoleniu „Brak kluczowych informacji w danych szkolenia — dodaj wiersze w sekcji „Kluczowe informacje" danych produktu (pod treścią). Na stronie blok się nie wyświetla.", poza szkoleniem „Tabela z danych działa tylko na stronie szkolenia — przełącz blok na „Wstęp". Na stronie blok się nie wyświetla.".

## Przykład

```html
<!-- wp:feuer/kluczowe-informacje {"wariant":"tabela"} /-->

<!-- wp:feuer/kluczowe-informacje {"wariant":"wstep","lead":"Jesteśmy zespołem ekspertów specjalizujących się w doradztwie i szkoleniach BHP."} -->
<!-- wp:list -->
<ul class="wp-block-list"><!-- wp:list-item -->
<li>Mamy stały zespół ekspercki wspierany przez szeroką bazę trenerów i konsultantów z doświadczeniem branżowym.</li>
<!-- /wp:list-item -->
<!-- wp:list-item -->
<li>Współpracujemy z kancelarią prawną, dzięki czemu nasze rekomendacje są zawsze zweryfikowane prawnie.</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->
<!-- /wp:feuer/kluczowe-informacje -->
```
