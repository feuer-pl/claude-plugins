# feuer/dla-kogo-pozycja

„Pozycja" — pozycja bloku [feuer/dla-kogo](blok-dla-kogo.md): numer, opcjonalny tytuł, opis. Typ: T ([bloki.md](bloki.md), „Typy bloków").

## Gdzie

- **[5n37rf]** Wyłącznie wewnątrz `feuer/dla-kogo` ([bloki.md](bloki.md), [raemfr]); bez blokady i zapisu jako blok wielokrotnego użytku ([bloki.md](bloki.md), [ecp7bd]).

## Pola

| ID | Pole | Atrybut | Rodzaj | Dozwolone | Limit | Wymagane / domyślne |
|---|---|---|---|---|---|---|
| **[xjuxb6]** | Tytuł (H3) | `tytul` | tekst jednowierszowy | bez formatów | 40 | opcjonalne — pusty (po `trim`) się nie wyświetla; na froncie bez znaczników HTML |
| **[u95scw]** | Opis | `opis` | tekst z łamaniem wiersza | pogrubienie, kursywa (na froncie wyłącznie `strong`, `em`, `br`) | 100 | obowiązkowe |

## Dane

- **[skuwgz]** Wiersze opisu oddzielone łamaniem wiersza — osobne akapity (`p`); wyrównanie między pozycjami — [README rodzica](blok-dla-kogo.md), [pv87q2].

## Edytor

- **[fe3t6e]** Pusty tytuł (podpowiedź „Tytuł (opcjonalny)…") widoczny w kanwie tylko przy zaznaczonej pozycji; poza tym kanwa = front.

## Przykład

```html
<!-- wp:feuer/dla-kogo-pozycja {"tytul":"Firmy wchodzące do Polski","opis":"Nie znasz polskich przepisów BHP? Zadbamy o zgodność i wyjaśnimy różnice między regulacjami w Twoim kraju i Polsce."} /-->
```
