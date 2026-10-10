# feuer/faq-pytanie

„Pytanie" — pytanie bloku [feuer/faq](blok-faq.md) z odpowiedzią. Typ: T ([bloki.md](bloki.md), „Typy bloków").

## Gdzie

- **[gadwmc]** Wyłącznie wewnątrz `feuer/faq` ([bloki.md](bloki.md), [raemfr]); bez blokady i zapisu jako blok wielokrotnego użytku ([bloki.md](bloki.md), [ecp7bd]).

## Pola

| ID | Pole | Atrybut | Rodzaj | Dozwolone | Limit | Wymagane / domyślne |
|---|---|---|---|---|---|---|
| **[cu5ckn]** | Pytanie | `pytanie` | tekst jednowierszowy | kursywa | bez limitu (bez licznika) | obowiązkowe — pusty: znacznik `<wprowadź dane>` w edytorze i w przycisku akordeonu |
| **[bjbfpq]** | Odpowiedź | bloki wewnętrzne | strefa treści; typografia treści redakcyjnej (A40, `.tresc`) | `core/paragraph` (także style „Lead", „Wyróżnienie", „Wyróżnienie z linią", „Hasło" — [paleta-tresci.md](paleta-tresci.md)), `core/list` z zagnieżdżaniem; ograniczenia i formaty jak w palecie | — | obowiązkowe — bez tekstu: panel z akapitem `<wprowadź dane>` |

## Dane

- **[9f4z46]** Pozycja: `div.faq-pozycja` — `h3` z przyciskiem akordeonu (`aria-expanded="false"`, `aria-controls` — panel odpowiedzi) i panel `.faq-odpowiedz.tresc` z unikalnym `id` (`faq-odpowiedz-N`), na starcie `hidden`. W pytaniu na froncie zostaje wyłącznie kursywa (`em`).

## Edytor

- **[rs5r8g]** Pytanie w stanie otwartym: nagłówek — `div` z `aria-expanded="true"` (lustro przycisku), odpowiedź widoczna i edytowalna; bez przełączania akordeonu.

## Przykład

```html
<!-- wp:feuer/faq-pytanie {"pytanie":"Czym jest analiza wypadku metodą drzewa przyczyn?"} -->
<!-- wp:paragraph -->
<p>To graficzna, systematyczna metoda badania wypadku, która rekonstruuje łańcuch faktów prowadzących do zdarzenia i pokazuje logiczne powiązania między nimi.</p>
<!-- /wp:paragraph -->
<!-- /wp:feuer/faq-pytanie -->
```
