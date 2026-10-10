# feuer/faq

„FAQ" — sekcja na tle wyróżnionym: nagłówek i lista pytań rozwijanych ([feuer/faq-pytanie](blok-faq-pytanie.md)). Typ: T ([bloki.md](bloki.md), „Typy bloków"). Akordeon: [bloki.md](bloki.md), „Zakładki i akordeon"; dane strukturalne `FAQPage`: [seo.md](seo.md), „FAQPage".

## Gdzie

- **[5pyjzz]** Samodzielna sekcja pełnej szerokości w treści stron i produktów, poza paletą treści redakcyjnej; najwyżej jedna w treści wpisu (`supports.multiple: false`).

## Pola

| ID | Pole | Atrybut | Rodzaj | Dozwolone | Limit | Wymagane / domyślne |
|---|---|---|---|---|---|---|
| **[u8xg88]** | Nagłówek (H2, w całości ExtraBold) | `tytul` | tekst z łamaniem wiersza | „Akcent w nagłówkach — bez akcentu" ([bloki.md](bloki.md), [bmw7u4]) | — | pusty — „Często zadawane pytania" przez i18n: na froncie także, gdy po usunięciu znaczników zostają same spacje; w edytorze (jako edytowalna wartość pola) — tylko przy całkiem pustym polu |
| **[x83wsu]** | Pytania | bloki wewnętrzne | `feuer/faq-pytanie`, dodawanie swobodne (`templateLock: false`) | wyłącznie `feuer/faq-pytanie` | bez górnego limitu | min. 1 — usunięcie ostatniego przywraca jedno puste; po wstawieniu 1 |

## Dane

- **[npkpg3]** Skład: sekcja na tle wyróżnionym (`tlo-wyroznione`) z kontenerem — nagłówek H2 i lista pytań; na froncie akordeon w trybie `akordeon` ([bloki.md](bloki.md), [h87yhn]) — na starcie wszystkie pytania zwinięte.

## Edytor

- **[swjk5c]** Pod listą pytań przycisk „Dodaj pytanie" (zamiast domyślnego „+") — dodaje pytanie na końcu; na froncie go nie ma.

## Przykład

```html
<!-- wp:feuer/faq -->
<!-- wp:feuer/faq-pytanie {"pytanie":"Czym jest analiza wypadku metodą drzewa przyczyn?"} -->
<!-- wp:paragraph -->
<p>To graficzna, systematyczna metoda badania wypadku, która rekonstruuje łańcuch faktów prowadzących do zdarzenia i pokazuje logiczne powiązania między nimi.</p>
<!-- /wp:paragraph -->
<!-- /wp:feuer/faq-pytanie -->
<!-- wp:feuer/faq-pytanie {"pytanie":"Jaka jest podstawa prawna i metodyczna takiej analizy?"} -->
<!-- wp:paragraph -->
<p>Analiza wpisuje się w obowiązek ustalania przyczyn wypadków i profilaktyki, najważniejsze poniżej:</p>
<!-- /wp:paragraph -->
<!-- wp:list {"ordered":true} -->
<ol class="wp-block-list"><!-- wp:list-item -->
<li>Kodeks pracy: obowiązek ustalenia okoliczności i przyczyn wypadku oraz zastosowania środków zapobiegawczych (art. 234);</li>
<!-- /wp:list-item -->
<!-- wp:list-item -->
<li>powiązanie: wyniki analizy zasilają protokół powypadkowy i wnioski profilaktyczne pracodawcy.</li>
<!-- /wp:list-item --></ol>
<!-- /wp:list -->
<!-- /wp:feuer/faq-pytanie -->
<!-- /wp:feuer/faq -->
```
