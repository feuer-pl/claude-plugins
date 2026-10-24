# feuer/kalendarium

„Kalendarium" — sekcja z nagłówkiem, leadem i do 4 kartami produktów (szkoleń i usług) z najbliższych oznaczonych miesięcy. Typ: D ([bloki.md](bloki.md), „Typy bloków"); jedno źródło bez wyboru: [bloki.md](bloki.md), [fejddw]; najbliższy oznaczony miesiąc i losowa kolejność: [bloki.md](bloki.md), [m5z6sd], [j9x79h]; oznaczenia miesięcy: [taksonomie.md](taksonomie.md); prewypełnienie layeru: formularz-kontaktu.md, [g3heqp].

## Gdzie

- **[tergua]** Samodzielna sekcja w treści stron: strona główna (w miejscu Terminów), tymczasowo strony branży i filarów; na każdej stronie ta sama pula — cała oferta, bez ustawień źródła.
- **[bxej44]** Osobny blok od Terminów: karty z markupem i CSS kart Terminów (sekcja z klasami `terminy kalendarium`, różnice w `css/kalendarium.css`), w miejscu etykiety — nazwa produktu.

## Pola

| ID | Pole | Atrybut | Rodzaj | Dozwolone | Limit | Wymagane / domyślne |
|---|---|---|---|---|---|---|
| **[e5uv5m]** | Nagłówek (H2) | `tytul` | tekst z łamaniem wiersza, w miejscu | „Akcent w nagłówkach" ([bloki.md](bloki.md), [s56shy]) | — | obowiązkowe, bez tekstu domyślnego |
| **[97btfw]** | Lead | `lead` | tekst z łamaniem wiersza, podpowiedź „Lead (opcjonalny)…"; na froncie łamanie usuwane | pogrubienie | — | opcjonalne — pusty (także same znaczniki lub spacje) się nie wyświetla |
| **[z5m6uw]** | Tekst przycisku „Zamów" — wspólny dla kart usług i szkoleń z terminem | `zamow` | tekst jednowierszowy, w miejscu na kartach | bez formatów | — | pusty (także same znaczniki lub spacje) — „Zamów" (i18n) |
| **[p9nznu]** | Tekst przycisku „Uzgodnij termin" — wspólny dla kart szkoleń bez terminu | `uzgodnij` | tekst jednowierszowy, w miejscu na kartach | bez formatów | — | pusty — „Uzgodnij termin" (i18n) |

## Dane

- **[cqktjt]** Pula: opublikowane produkty (szkolenia i usługi) z co najmniej jednym oznaczeniem miesiąca (samo „TOP 20" nie wystarcza), bez flagi „Nie pokazuj w listingu kategorii" ([produkt.md](produkt.md), [999uaf]); jedna karta = jeden produkt, raz — w najbliższym ze swoich miesięcy ([bloki.md](bloki.md), [m5z6sd]).
- **[j3svr5]** Do 4 kart: miesiące po kolei od bieżącego, aż zbierze się 4 — miesiąc rozpoczęty przed osiągnięciem 4 kart trafia do renderu w całości, dalsze są pomijane; w obrębie miesiąca losowanie w przeglądarce przy każdym wczytaniu (`uloz.js`), karty w kolejności miesięcy. Mniej produktów — tyle kart, ile jest, bez powtórzeń; brak produktów — zachowanie wg [bloki.md](bloki.md), [szj5f5].
- **[pa284q]** Karta: czerwony element — miesiąc i rok, z którego produkt jest pokazany („F Y" wielką literą, np. „Październik 2026", `<time datetime="Y-m">`), bez szarego wiersza; tytuł (`h3`) — nazwa na karcie ([produkt.md](produkt.md), [hh6g67]), link do strony produktu.
- **[ctwd7y]** Szkolenie z aktualnym terminem — najbliższy aktualny termin ([produkt.md](produkt.md), [d566w4]; także w kolejnym miesiącu niż miesiąc karty): forma (słownik, pogrubiona), data („j F Y", np. „15 października 2026") i opis terminu z łamaniami; przycisk `zamow`. Szkolenie bez aktualnego terminu — „Opis na karcie" (`_feuer_opis_karty`) i przycisk `uzgodnij`. Usługa i produkt bez rodzaju — „Opis na karcie" i przycisk `zamow`, bez terminu.
- **[yp926z]** Przycisk karty otwiera layer kontaktu (formularz-kontaktu.md, [g3heqp]), a karta z terminem szkolenia gotowego do zapisu — formularz zapisu (formularz-zapisu.md, [53y98g]); `aria-label` „<tekst przycisku>: <nazwa>, <data terminu>" (bez terminu — „<tekst przycisku>: <nazwa>"); po tekście ikona strzałki (`i-strzalka`).

## Edytor

- **[tyf5c4]** Lustrzany markup frontu z edycją tekstów w miejscu; karty układa ta sama logika co front (`uloz.js`: kolejność miesięcy, losowanie, limit 4); brak produktów — w miejscu kart „Brak produktów z oznaczeniem miesiąca — na stronie blok się nie wyświetla.".

## Wielojęzyczność

- **[xb3gza]** Miesiące, daty i forma terminu przez i18n (`_x`, `wp_date`, słownik formy); reszta wg [bloki.md](bloki.md), [49nkuy].

## Przykład

```html
<!-- wp:feuer/kalendarium {"tytul":"\u003cspan class=\u0022akcent\u0022\u003e\u003cspan class=\u0022akcent-marki\u0022\u003e”\u003c/span\u003eNie wiedziałem\u003cspan class=\u0022akcent-marki\u0022\u003e”\u003c/span\u003e\u003cbr\u003eto nie jest poprawna odpowiedź w BHP.\u003c/span\u003e\u003cbr\u003eSprawdź co jest teraz ważne."} /-->
```
