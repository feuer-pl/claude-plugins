# feuer/zgoda

„Zgoda RODO" — treść zgody RODO layeru kontaktu: jeden tekst formatowany wspólny dla serwisu, w sekcji `zgoda-rodo`. Typ: T ([bloki.md](bloki.md), „Typy bloków"). Checkbox zgody, etykieta i opis, odczyt treści, wiadomość i log: formularz-kontaktu.md; sekcja i blokada struktury: [sekcje.md](sekcje.md), [apz8vx].

## Gdzie

- **[69brke]** Wyłącznie w sekcji `zgoda-rodo`: poza wstawiaczem, raz w treści (`multiple: false`), bez zapisu jako blok wielokrotnego użytku ([bloki.md](bloki.md), [ecp7bd]).

## Pola

| ID | Pole | Atrybut | Rodzaj | Dozwolone | Limit | Wymagane / domyślne |
|---|---|---|---|---|---|---|
| **[s55cmq]** | Tekst zgody: pierwszy akapit — etykieta checkboxa, kolejne bloki — opis | bloki wewnętrzne | strefa treści (tekst formatowany — [bloki.md](bloki.md), [c3atk4]) | skład wg [bloki.md](bloki.md), [rg4r9f] | — | obowiązkowe |

## Dane

- **[f7up2y]** Bez własnego renderu (`save` zapisuje bloki wewnętrzne); odczyt i obsługa treści: formularz-kontaktu.md, [r2ag7x].
- **[3dkf7s]** Treść początkowa sekcji ([sekcje.md](sekcje.md), [rrzbuy]) — przykład niżej; np. WP-CLI `wp post create - --post_type=sekcja --post_title="Zgoda RODO" --post_name=zgoda-rodo --post_status=publish` z treścią na wejściu.

## Edytor

- **[dgbrug]** Lustrzany markup zgody: checkbox bez działania, tekst edytowany w miejscu, gwiazdka zgody obowiązkowej za pierwszym akapitem, szerokość treści karty layeru na desktopie.
- **[djujsu]** Pierwszy blok zawsze akapitem z blokadą usuwania i przesuwania: blok wstawiony nad nim edytor przenosi tuż pod niego; pusty blok dostaje akapit z blokadą i znacznikiem `<wprowadź dane>` (bez oznaczania zmiany); pierwszy akapit bez blokady dostaje blokadę; pierwszy blok niebędący akapitem — edytor wstawia na początku nowy zablokowany akapit. Pod nim akapity i listy dowolnie.

## Przykład

```html
<!-- wp:feuer/zgoda -->
<!-- wp:paragraph {"lock":{"move":true,"remove":true}} -->
<p>Wyrażam zgodę na przetwarzanie moich danych osobowych w celu kontaktu elektronicznego lub mailowego w celu przedstawienia oferty marketingowej przez Feuer Sp. z o.o.</p>
<!-- /wp:paragraph -->
<!-- /wp:feuer/zgoda -->
```
