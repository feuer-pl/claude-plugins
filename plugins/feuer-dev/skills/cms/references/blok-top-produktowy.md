# feuer/top-produktowy

„Top visual produktowy" — sekcja otwierająca strony produktu: etykieta kategorii, H1, lead, rząd zamówienia (pola wyboru wariantu i terminu, przycisk „Zamów", link do artykułu produktu) i zdjęcie. Typ: D + T ([bloki.md](bloki.md), „Typy bloków"). Wzorce produktu: [wzorce-stron.md](wzorce-stron.md), [m9behp]; warianty i terminy produktu: [produkt.md](produkt.md), [779j8w], [vvvvng]; prewypełnienie layeru: formularz-kontaktu.md, [utzf8f]; okruszki: [nawigacja.md](nawigacja.md), [xmubhb].

## Gdzie

- **[jq6avr]** Pierwsza pozycja wzorców startowych strony produktu, zablokowany atrybutem `lock` w bloku (bez przesuwania i usuwania); poza wstawiaczem (ręcznie wstawić się go nie da), jeden na stronę (`multiple: false`).

## Pola

| ID | Pole | Atrybut | Rodzaj | Dozwolone | Limit | Wymagane / domyślne |
|---|---|---|---|---|---|---|
| **[jkfn6w]** | Etykieta kategorii | `etykieta` | tekst jednowierszowy, w miejscu | bez formatów (na froncie bez znaczników) | 45 | obowiązkowe |
| **[b3uauw]** | H1 (w całości ExtraBold) | `tytul` | tekst z łamaniem wiersza, w miejscu | „Akcent w nagłówkach — bez akcentu" ([bloki.md](bloki.md), [bmw7u4]); na froncie `wp_kses_post` | 60 | opcjonalne — pusty (po usunięciu znaczników): tytuł wpisu (nazwa produktu zostaje dla SEO, list i okruszków) |
| **[xqrp9u]** | Lead | `lead` | tekst z łamaniem wiersza, w miejscu | pogrubienie (na froncie `strong`, `br`) | 320 | obowiązkowe |
| **[4ffr45]** | Tekst przycisku | `przycisk` | tekst jednowierszowy, w miejscu | bez formatów | — | pusty — „Zamów" (i18n) |
| **[puqw98]** | Tekst linku do artykułu | `etykietaLinku` | tekst jednowierszowy, w miejscu | bez formatów | — | pusty — „Dowiedz się więcej" (i18n) |
| **[r4hwp8]** | Zdjęcie | obrazek wyróżniający wpisu (bez pola w bloku) | medium | obrazy | — | obowiązkowe — brak albo usunięty: stan „bez zdjęcia" (`.scena-zdjecie.bez-zdjecia` — [strony-zbiorcze.md](strony-zbiorcze.md), [3dh7tn]) i zgłoszenie pustego pola `obrazek` ([bloki.md](bloki.md), [aast68]); `loading="eager"` i `fetchpriority="high"` ([media.md](media.md), [s4ae2p]) |
| **[t6t4te]** | Szerokość tła | `szerokoscTla` | panel „Ustawienia" — wspólne ustawienie szerokości tła: css.md, [k34pyh] | `1440`, `1920` | — | `1440` |

- **[trpyjp]** Podpowiedzi pól wyboru („Wybierz wariant", „Termin") — zaszyte w kodzie (i18n) jako etykiety formularza.

## Dane

- **[vrnn3b]** Dane z wpisu z kontekstu bloku (`postId`, `postType`); bez identyfikatora wpisu blok nic nie renderuje.
- **[jsxm7f]** Rząd zamówienia (układ z danych, bez ustawienia odmiany): pole wyboru wariantu — tylko szkolenie z niepustą listą wariantów (opcje — nazwy wariantów); pole terminu — tylko szkolenie z aktualnymi terminami (opcje „j F Y"); przycisk „Zamów" (`button.przycisk.przycisk-strzalka`, wyzwalacz layeru kontaktu, a przy szkoleniu gotowym do zapisu — formularza zapisu: formularz-zapisu.md, [t472my]) — zawsze.
- **[k26qth]** Link „Dowiedz się więcej" (link akcji ze strzałką, A43) — do powiązanego artykułu produktu (`_feuer_artykul`; adres w języku strony: [wielojezycznosc.md](wielojezycznosc.md), [b8tb5u]), tylko gdy artykuł istnieje i jest opublikowany; przy polach wyboru stoi osobną linią nad nimi, bez pól — w rzędzie za przyciskiem.
- **[qu9w2v]** Pola wyboru — atom A53 ([bloki.md](bloki.md), [3r3tf7]): lista `role="listbox"`, opcje `role="option"`.

## Edytor

- **[vmc4qy]** Lustrzany markup z edycją tekstów w miejscu; pole wariantu i pole terminu statycznie, gdy produkt ma warianty albo aktualne terminy; tekst przycisku i linku w elementach `span` ([bloki.md](bloki.md), [pufx5c]); etykieta — zewnętrzny `span.etykieta-kategorii` i wewnętrzny `span` pola ([bloki.md](bloki.md), [jtnzgj]).
- **[a5bggj]** Pierwsza edycja H1 zapisuje cały wyświetlany tekst w `tytul` — od tej chwili H1 nie podąża za tytułem wpisu.

## Przykład

```html
<!-- wp:feuer/top-produktowy {"lock":{"move":true,"remove":true},"etykieta":"Szkolenia z prawa pracy","tytul":"Pewne decyzje kadrowe na aktualnym prawie","lead":"Prawo pracy zmienia się co roku: praca zdalna, nowe urlopy, jawność wynagrodzeń. Uczymy kadry i kierowników stosować przepisy pewnie i sprawnie."} /-->
```
