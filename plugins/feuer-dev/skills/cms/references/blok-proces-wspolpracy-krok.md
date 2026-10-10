# feuer/proces-wspolpracy-krok

„Krok" — krok bloku [feuer/proces-wspolpracy](blok-proces-wspolpracy.md): numer, opcjonalna ikona, tytuł, opis. Typ: T ([bloki.md](bloki.md), „Typy bloków").

## Gdzie

- **[22qwra]** Wyłącznie wewnątrz `feuer/proces-wspolpracy` ([bloki.md](bloki.md), [raemfr]); bez blokady i zapisu jako blok wielokrotnego użytku ([bloki.md](bloki.md), [ecp7bd]); `save` = `null`.

## Pola

| ID | Pole | Atrybut | Rodzaj | Dozwolone | Limit | Wymagane / domyślne |
|---|---|---|---|---|---|---|
| **[ndpyef]** | Ikona (dekoracyjna, `alt=""`, `loading="lazy"`; poświata z CSS tylko przy ikonie) | `ikona` (ID pliku) | medium — toolbar kroku: „Wybierz ikonę" / „Zmień ikonę", „Resetuj" | dowolny plik obrazu z biblioteki mediów — zgodność ze stylem ikon ilustracyjnych 48 po stronie redakcji, blok jej nie sprawdza | — | opcjonalne; brak albo plik usunięty z biblioteki — sam numer, bez ikony i poświaty (front i edytor) |
| **[ky2ydu]** | Tytuł (H3) | `tytul` | tekst jednowierszowy | bez formatów | 35 | obowiązkowe |
| **[mmwsqx]** | Opis (`p.proces-opis`) | `opis` | tekst z łamaniem wiersza | pogrubienie, kursywa (na froncie `strong`, `em`, `br`) | 200 | obowiązkowe |

- **[3xdcbb]** Numer kroku („01." — zera wiodące, kropka) z licznika CSS, nie jest polem bloku.

## Przykład

```html
<!-- wp:feuer/proces-wspolpracy-krok {"ikona":123,"tytul":"Dobór i role koordynatorów","opis":"Pomagamy dobrać właściwe osoby i podzielić obiekt na obszary odpowiedzialności, tak by każde piętro lub strefa miały swojego lidera."} /-->
```
