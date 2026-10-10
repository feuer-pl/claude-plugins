# feuer/stopka

„Stopka serwisu" — zamknięty blok stopki: pas certyfikatów, przycisk „Do góry", logo, e-mail, linki social, linki pomocnicze, „Oferta" z taksonomii i pasek prawny. Typ: R + D ([bloki.md](bloki.md), „Typy bloków"); blok ramy: [bloki.md](bloki.md), [bfdf6a]; sekcja `stopka-serwisu`: [sekcje.md](sekcje.md), [78a65y]; drzewo oferty: [nawigacja.md](nawigacja.md), [2b9qxk].

## Gdzie

- **[kxqtkv]** Wyłącznie w sekcji `stopka-serwisu` (część szablonu `stopka` — każda strona z WordPressa): poza wstawiaczem, bez zapisu jako blok wielokrotnego użytku ([bloki.md](bloki.md), [ecp7bd]), bez wyrównania.

## Pola

| ID | Pole | Atrybut | Rodzaj | Dozwolone | Limit | Wymagane / domyślne |
|---|---|---|---|---|---|---|
| **[83bs8x]** | E-mail | `email` | pole e-mail (panel „Kontakt") | adres e-mail | — | pusty albo nieprawidłowy (po `sanitize_email`) — niewyświetlany; na froncie link `mailto:` |
| **[sb44bg]** | Linki pomocnicze | `linkiPomocnicze` | lista: etykieta + link ([bloki.md](bloki.md), [9s9332], [4svhm3]) | wpis serwisu albo adres | — | pusta |
| **[dtvnh9]** | Linki paska prawnego | `linkiPrawne` | lista: etykieta + link (jak wyżej) | wpis serwisu albo adres | — | pusta |
| **[wh6yky]** | Certyfikaty (pas certyfikatów) | `certyfikaty`: `obrazId`, `alt`, link | lista pozycji: obraz z biblioteki mediów, tekst alternatywny (wpisywany w pozycji), opcjonalny link | obrazy | — | pusta; pozycja bez obrazu (niewybranego albo usuniętego) pominięta; bez pozycji — pusty biały pas |
| **[5wtzqn]** | Prawa autorskie | `prawa` | tekst z łamaniem wiersza, w miejscu | „Krótki tekst" ([bloki.md](bloki.md), [nmwmdu], [taeeq4]) | — | pusty (także same łamania i spacje) — „Feuer. Wszystkie prawa zastrzeżone" przez i18n; `© {bieżący rok}` (rok z `wp_date`) wstawia render przed polem |

- **[vhqfqv]** Edycja — [bloki.md](bloki.md), [bfdf6a] (panel boczny i prawa autorskie w miejscu); panel „Kontakt" ma wiersz z odnośnikiem „Ustawienia → Feuer" (nowa karta) — linki social żyją w ustawieniach serwisu.

## Dane

- **[p56emp]** Zaszyte (nieedytowalne): logo — link do strony głównej (etykieta dostępności „Feuer — strona główna", i18n); przycisk „Do góry" (tekst i18n, `href="#"`, płynne przewinięcie z `scroll-behavior: smooth`) na styku pasa certyfikatów i ciemnej części stopki; nagłówek „Oferta" (H2, i18n — [bloki.md](bloki.md), [8464y5]).
- **[wkj377]** Ikony social (Facebook, Instagram, YouTube, LinkedIn — w tej kolejności) z opcji `feuer_social` ([ustawienia.md](ustawienia.md), [rrgwk9]).
- **[u8gepb]** „Oferta": drzewo taksonomii `oferta` (jak menu; taksonomia nietłumaczona — [wielojezycznosc.md](wielojezycznosc.md), [7n3mcs]) — kategorie najwyższego poziomu jako grupy (nazwa — link do strony kategorii), pod nimi bezpośrednie podkategorie (linki do swoich stron).
- **[gqdhmj]** Rozkład „Oferty" — automatyczny, tymczasowy (pytanie otwarte 30, pytania-otwarte.md): maksymalnie 3 kolumny, zachłannie po kolei — grupa, która przepełniłaby 1/3 wierszy (waga grupy = 1 + liczba podkategorii), otwiera kolejną kolumnę.
- **[vtr98g]** Poniżej 1024 px grupy z podkategoriami to akordeony: nazwa kategorii zostaje linkiem, obok niej osobny przycisk z chevronem (`data-rozwijane="akordeon"`, `aria-label` „Podkategorie: …", `aria-controls` na listę; domyślnie rozwinięte) — tylko przy kategoriach z podkategoriami, od 1024 px ukryty; kategoria bez podkategorii — sam link. Zachowanie akordeonu — [nawigacja.md](nawigacja.md), [p6ug2v].

## Edytor

- **[mz993a]** Lustrzany szkielet: części z danych (certyfikaty, część główna, linki prawne, rok, sprite ikon) — z `render.php` (JSON), prawa autorskie edytowane w miejscu; część główna w wrapperze `display: contents` (pozycje siatki `.kontener` — wiersz praw autorskich nie rozbija `grid-template-areas`); linki w kanwie — [bloki.md](bloki.md), [ap7hv3].

## Wielojęzyczność

- **[udvg9x]** Sekcja `stopka-serwisu` — jedna dla wszystkich języków (typ `sekcja` nietłumaczony: [sekcje.md](sekcje.md), [8bcbuy]): e-mail, linki, certyfikaty i prawa autorskie wspólne (pusty tekst — domyślny przez i18n); linki social wspólne; „Oferta" — taksonomia nietłumaczona ([wielojezycznosc.md](wielojezycznosc.md), [7n3mcs]).

## Przykład

```html
<!-- wp:feuer/stopka {"email":"kontakt@feuer.pl","linkiPomocnicze":[{"etykieta":"O firmie","url":"https://feuer.pl/o-firmie/","id":6}],"linkiPrawne":[{"etykieta":"Polityka bezpieczeństwa","url":"https://feuer.pl/polityka-bezpieczenstwa/","id":11},{"etykieta":"Dane osobowe","url":"https://feuer.pl/dane-osobowe/","id":12}],"certyfikaty":[{"obrazId":120,"alt":"ISO 9001"}],"prawa":"Feuer sp. z o.o. Wszystkie prawa zastrzeżone"} /-->
```
