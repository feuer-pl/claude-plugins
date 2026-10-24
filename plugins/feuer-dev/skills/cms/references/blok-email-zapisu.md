# feuer/email-zapisu

„E-mail zapisu na szkolenie" — tekst e-maila potwierdzenia, który klient dostaje po zapisie na szkolenie otwarte: jeden tekst formatowany na wariant formularza, w sekcjach `email-zapisu` i `email-zapisu-sep`. Typ: T ([bloki.md](bloki.md), „Typy bloków"). E-mail, dane zgłoszenia i załącznik: formularz-zapisu.md, [yn2wre]; sekcje i blokada struktury: [sekcje.md](sekcje.md), [sb2whm], [myw3kd].

## Gdzie

- **[uv3sx7]** Wyłącznie w sekcjach `email-zapisu` i `email-zapisu-sep`: poza wstawiaczem, raz w treści (`multiple: false`), bez zapisu jako blok wielokrotnego użytku ([bloki.md](bloki.md), [ecp7bd]).

## Pola

| ID | Pole | Atrybut | Rodzaj | Dozwolone | Limit | Wymagane / domyślne |
|---|---|---|---|---|---|---|
| **[ttra3m]** | Tekst e-maila | bloki wewnętrzne | strefa treści (tekst formatowany — [bloki.md](bloki.md), [c3atk4]) | skład wg [bloki.md](bloki.md), [rg4r9f] | — | obowiązkowe |

## Dane

- **[zhbaxk]** Bez własnego renderu (`save` zapisuje bloki wewnętrzne); e-mail do klienta — HTML bloków wewnętrznych pierwszego bloku `feuer/email-zapisu` sekcji, pod nim dane zgłoszenia dopisywane przez serwis (formularz-zapisu.md, [yn2wre]). Warunki anulacji i inne informacje dla klienta — w tym tekście.
- **[kfmuxu]** Treść początkowa sekcji ([sekcje.md](sekcje.md), [rrzbuy]) — przykład niżej; np. WP-CLI `wp post create - --post_type=sekcja --post_title="E-mail zapisu na szkolenie" --post_name=email-zapisu --post_status=publish` (sekcja SEP: tytuł „E-mail zapisu na szkolenie z SEP", slug `email-zapisu-sep`) z treścią na wejściu. Tekst e-maila dostarcza Feuer.

## Edytor

- **[58re6h]** Tekst edytowany w miejscu, szerokość 40rem; pod nim szara informacja „Pod tekstem e-mail zawiera dane zgłoszenia (szkolenie, termin, liczba miejsc, koszt, dane do faktury, adres wysyłki) — dopisuje je serwis.". Blok bez bloków wewnętrznych dostaje pusty akapit ze znacznikiem `<wprowadź dane>` (bez oznaczania zmiany).

## Przykład

```html
<!-- wp:feuer/email-zapisu -->
<!-- wp:paragraph -->
<p>Dziękujemy za zgłoszenie na szkolenie. W załączniku przesyłamy wzór listy uczestników — prosimy o odesłanie danych uczestników w odpowiedzi na tę wiadomość.</p>
<!-- /wp:paragraph -->
<!-- /wp:feuer/email-zapisu -->
```
