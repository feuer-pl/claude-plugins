# feuer/klauzula-rodo

„Klauzula RODO formularza zapisu" — klauzula informacyjna RODO pod zgodą marketingową formularza zapisu na szkolenie otwarte: jeden tekst formatowany, w sekcji `klauzula-zapisu`. Typ: T ([bloki.md](bloki.md), „Typy bloków"). Miejsce w formularzu i odczyt: formularz-zapisu.md, [vpdvma]; sekcja i blokada struktury: [sekcje.md](sekcje.md), [kun9dh].

## Gdzie

- **[2snayp]** Wyłącznie w sekcji `klauzula-zapisu`: poza wstawiaczem, raz w treści (`multiple: false`), bez zapisu jako blok wielokrotnego użytku ([bloki.md](bloki.md), [ecp7bd]).

## Pola

| ID | Pole | Atrybut | Rodzaj | Dozwolone | Limit | Wymagane / domyślne |
|---|---|---|---|---|---|---|
| **[dybjw9]** | Tekst klauzuli | bloki wewnętrzne | strefa treści (tekst formatowany — [bloki.md](bloki.md), [c3atk4]) | skład wg [bloki.md](bloki.md), [rg4r9f] | — | obowiązkowe |

## Dane

- **[dagp6f]** Bez własnego renderu (`save` zapisuje bloki wewnętrzne); formularz pokazuje HTML bloków wewnętrznych (formularz-zapisu.md, [vpdvma]).
- **[pjyu32]** Treść początkowa sekcji ([sekcje.md](sekcje.md), [rrzbuy]) — przykład niżej (tekst z uwag Feuer, link do strony „Dane osobowe"); np. WP-CLI `wp post create - --post_type=sekcja --post_title="Klauzula RODO formularza zapisu" --post_name=klauzula-zapisu --post_status=publish` z treścią na wejściu.

## Edytor

- **[daw5cc]** Tekst edytowany w miejscu, drobny i szary jak w formularzu, szerokość 35rem. Blok bez bloków wewnętrznych dostaje pusty akapit ze znacznikiem `<wprowadź dane>` (bez oznaczania zmiany).

## Przykład

```html
<!-- wp:feuer/klauzula-rodo -->
<!-- wp:paragraph -->
<p>Administratorem danych osobowych jest Feuer sp. z o.o. Dane podane w formularzu będą przetwarzane w celu obsługi zgłoszenia na szkolenie, kontaktu w sprawach organizacyjnych oraz realizacji udziału w szkoleniu. Szczegółowe informacje dotyczące przetwarzania danych znajdują się w <a href="/dane-osobowe/">Polityce prywatności</a>.</p>
<!-- /wp:paragraph -->
<!-- /wp:feuer/klauzula-rodo -->
```
