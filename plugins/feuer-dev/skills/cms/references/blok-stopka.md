# feuer/stopka

„Stopka serwisu" — zamknięty blok stopki: pas certyfikatów, przycisk „Do góry", logo, dane firmy (e-mail, telefony, nazwa prawna, adres, NIP), linki social, linki pomocnicze, „Oferta" z taksonomii i pasek prawny. Typ: R + D ([bloki.md](bloki.md), „Typy bloków"); blok ramy: [bloki.md](bloki.md), [bfdf6a]; sekcja `stopka-serwisu`: [sekcje.md](sekcje.md), [78a65y]; drzewo oferty: [nawigacja.md](nawigacja.md), [2b9qxk].

## Gdzie

- **[kxqtkv]** Wyłącznie w sekcji `stopka-serwisu` (część szablonu `stopka` — każda strona z WordPressa): poza wstawiaczem, bez zapisu jako blok wielokrotnego użytku ([bloki.md](bloki.md), [ecp7bd]), bez wyrównania.

## Pola

| ID | Pole | Atrybut | Rodzaj | Dozwolone | Limit | Wymagane / domyślne |
|---|---|---|---|---|---|---|
| **[sb44bg]** | Linki pomocnicze | `linkiPomocnicze` | lista: etykieta + link ([bloki.md](bloki.md), [9s9332], [4svhm3]) | wpis serwisu albo adres | — | pusta |
| **[dtvnh9]** | Linki paska prawnego | `linkiPrawne` | lista: etykieta + link (jak wyżej) | wpis serwisu albo adres | — | pusta |
| **[wh6yky]** | Certyfikaty (pas certyfikatów) | `certyfikaty`: `obrazId`, `alt`, link | lista pozycji: obraz z biblioteki mediów, tekst alternatywny (wpisywany w pozycji), opcjonalny link | obrazy | — | pusta; pozycja bez obrazu (niewybranego albo usuniętego) pominięta; bez pozycji — pusty biały pas |
| **[5wtzqn]** | Prawa autorskie | `prawa` | tekst z łamaniem wiersza, w miejscu | „Krótki tekst" ([bloki.md](bloki.md), [nmwmdu], [taeeq4]) | — | pusty (także same łamania i spacje) — „Feuer. Wszystkie prawa zastrzeżone" przez i18n; `© {bieżący rok}` (rok z `wp_date`) wstawia render przed polem |

- **[vhqfqv]** Edycja — [bloki.md](bloki.md), [bfdf6a] (panel boczny i prawa autorskie w miejscu); panel „Kontakt" ma sam wiersz z odnośnikiem „Ustawienia → Feuer" (nowa karta) — dane firmy i linki social żyją w ustawieniach serwisu.

## Dane

- **[p56emp]** Zaszyte (nieedytowalne): logo — link do strony głównej (etykieta dostępności „Feuer — strona główna", i18n); przycisk „Do góry" (tekst i18n, `href="#"`, płynne przewinięcie z `scroll-behavior: smooth`) na styku pasa certyfikatów i ciemnej części stopki; nagłówek „Oferta" (H2, i18n — [bloki.md](bloki.md), [8464y5]).
- **[83bs8x]** E-mail — pole „E-mail" danych organizacji (`feuer_organizacja`, [ustawienia.md](ustawienia.md), [p3qxtw]): link `mailto:`; pusty albo nieprawidłowy (po `sanitize_email`) — niewyświetlany.
- **[wy43yq]** Telefony — pole „Telefony" danych organizacji: wiersz pola = numer (przycięty, puste pomijane), w kolejności pola; link `tel:` — w adresie same cyfry i „+", tekst jak wpisany.
- **[dzef8w]** Nazwa prawna, adres (ulica; kod i miejscowość) i NIP (tekst „NIP {numer}", i18n) — pola danych organizacji, tekst bez linków.
- **[q7y6qj]** Od 1024 px: pod logo e-mail, pod nim telefony (każdy w osobnym wierszu), dalej ikony social; nazwa prawna, adres i NIP — drugi wiersz paska prawnego, pod prawami autorskimi: „{nazwa prawna} · {ulica}, {kod} {miejscowość} · NIP {numer}".
- **[sgw2jp]** Poniżej 1024 px: blok danych firmy między linkami pomocniczymi a logo, oddzielony linią jak pozostałe bloki — grupy z podpisami (i18n) „E-mail", „Telefon" (numery w osobnych wierszach), „Adres" (ulica; kod i miejscowość), „Dane firmy" (nazwa prawna; NIP), w dwóch kolumnach; pod logo same ikony social; pasek prawny bez danych firmy.
- **[hw2mma]** Puste pole danych organizacji — niewyświetlane: grupa bez danych znika razem z podpisem, pusta część wiersza paska prawnego — pominięta; wiersz bez żadnej danej i blok bez żadnej grupy — niewyświetlane.
- **[nb2hd8]** Markup ma oba układy danych firmy ([q7y6qj], [sgw2jp]); widoczny jest jeden, wg szerokości (`stopka.css`), drugi — `display: none`.
- **[wkj377]** Ikony social (Facebook, Instagram, YouTube, LinkedIn — w tej kolejności) z opcji `feuer_social` ([ustawienia.md](ustawienia.md), [rrgwk9]).
- **[u8gepb]** „Oferta": drzewo taksonomii `oferta` (jak menu; taksonomia nietłumaczona — [wielojezycznosc.md](wielojezycznosc.md), [7n3mcs]) — kategorie najwyższego poziomu jako grupy (nazwa — link do strony kategorii), pod nimi bezpośrednie podkategorie (linki do swoich stron).
- **[gqdhmj]** Rozkład „Oferty" — automatyczny, tymczasowy (pytanie otwarte 30, pytania-otwarte.md): maksymalnie 3 kolumny, zachłannie po kolei — grupa, która przepełniłaby 1/3 wierszy (waga grupy = 1 + liczba podkategorii), otwiera kolejną kolumnę.
- **[vtr98g]** Poniżej 1024 px grupy z podkategoriami to akordeony: nazwa kategorii zostaje linkiem, obok niej osobny przycisk z chevronem (`data-rozwijane="akordeon"`, `aria-label` „Podkategorie: …", `aria-controls` na listę; domyślnie rozwinięte) — tylko przy kategoriach z podkategoriami, od 1024 px ukryty; kategoria bez podkategorii — sam link. Zachowanie akordeonu — [nawigacja.md](nawigacja.md), [p6ug2v].

## Edytor

- **[mz993a]** Lustrzany szkielet: części z danych (certyfikaty, część główna z danymi firmy, linki prawne, wiersz danych firmy paska prawnego, rok, sprite ikon) — z `render.php` (JSON), prawa autorskie edytowane w miejscu; część główna w wrapperze `display: contents` (pozycje siatki `.kontener` — wiersz praw autorskich nie rozbija `grid-template-areas`); linki w kanwie — [bloki.md](bloki.md), [ap7hv3].

## Wielojęzyczność

- **[udvg9x]** Sekcja `stopka-serwisu` — jedna dla wszystkich języków (typ `sekcja` nietłumaczony: [sekcje.md](sekcje.md), [8bcbuy]): linki, certyfikaty i prawa autorskie wspólne (pusty tekst — domyślny przez i18n); dane firmy i linki social — ustawienia serwisu, jeden zestaw dla wszystkich języków ([ustawienia.md](ustawienia.md), [qa44d9]); „Oferta" — taksonomia nietłumaczona ([wielojezycznosc.md](wielojezycznosc.md), [7n3mcs]).

## Przykład

```html
<!-- wp:feuer/stopka {"linkiPomocnicze":[{"etykieta":"O firmie","url":"https://feuer.pl/o-firmie/","id":6}],"linkiPrawne":[{"etykieta":"Polityka bezpieczeństwa","url":"https://feuer.pl/polityka-bezpieczenstwa/","id":11},{"etykieta":"Dane osobowe","url":"https://feuer.pl/dane-osobowe/","id":12}],"certyfikaty":[{"obrazId":120,"alt":"ISO 9001"}],"prawa":"Feuer sp. z o.o. Wszystkie prawa zastrzeżone"} /-->
```
