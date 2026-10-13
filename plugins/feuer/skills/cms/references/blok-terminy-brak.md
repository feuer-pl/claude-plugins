# feuer/terminy-brak

„Terminy — stan pusty" — teksty stanu pustego bloku [feuer/terminy](blok-terminy.md): nagłówek, lead i tekst przycisku wyświetlane zamiast kart, gdy bieżące szkolenie nie ma aktualnych terminów. Typ: T ([bloki.md](bloki.md), „Typy bloków"). Sekcja i blokada struktury: [sekcje.md](sekcje.md), [96pxac].

## Gdzie

- **[u4vkk5]** Wyłącznie w sekcji `terminy-brak`: poza wstawiaczem, raz w treści (`multiple: false`), bez zapisu jako blok wielokrotnego użytku ([bloki.md](bloki.md), [ecp7bd]). Jedno miejsce dla serwisu — zmiana w sekcji zmienia stan pusty wszystkich Terminów (wyjątek od edycji tekstów bloku w miejscu: [bloki.md](bloki.md), [3g9tqb]).

## Pola

| ID | Pole | Atrybut | Rodzaj | Dozwolone | Limit | Wymagane / domyślne |
|---|---|---|---|---|---|---|
| **[uew68a]** | Nagłówek (H2) | `tytul` | tekst z łamaniem wiersza | „Akcent w nagłówkach" ([bloki.md](bloki.md), [s56shy]) | — | obowiązkowe |
| **[tsrtnv]** | Lead | `lead` | tekst z łamaniem wiersza; na froncie łamanie usuwane | pogrubienie | — | opcjonalne — pusty się nie wyświetla |
| **[bnxh2c]** | Tekst przycisku | `przycisk` | tekst jednowierszowy | bez formatów | — | obowiązkowe — pusty: przycisk ze znacznikiem `<wprowadź dane>`, bez otwierania layeru kontaktu |

## Dane

- **[vzx2cq]** Bez własnego renderu (`save` = `null`): pola czyta render bloku `feuer/terminy` ([README terminy](blok-terminy.md), [vqnsvw]). Przycisk otwiera layer kontaktu — prewypełnienie: formularz-kontaktu.md, [7x4m9c].
- **[4h84zc]** Treść początkowa sekcji = przykład niżej ([sekcje.md](sekcje.md), [rrzbuy]); np. WP-CLI `wp post create - --post_type=sekcja --post_name=terminy-brak --post_status=publish` z treścią na wejściu.

## Edytor

- **[nrwfhe]** Lustrzany markup stanu pustego z edycją tekstów w miejscu, przycisk bez działania (prewypełnienie layeru istnieje dopiero na stronie szkolenia); pusty lead — podpowiedź „Lead (opcjonalny)…".

## Przykład

```html
<!-- wp:feuer/terminy-brak {"tytul":"Termin dopasujemy do Ciebie","lead":"Obecnie nie mamy otwartych terminów tego szkolenia. Napisz do nas — ustalimy termin dopasowany do Twojej firmy.","przycisk":"Zapytaj o termin"} /-->
```
