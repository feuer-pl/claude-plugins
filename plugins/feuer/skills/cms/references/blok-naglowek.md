# feuer/naglowek

„Header serwisu" — zamknięty blok headera z menu głównym: logo, linki pomocnicze, przycisk (E-learning), menu desktop (mega-panele z drzewa oferty) i mobile, przełącznik języka (wyłączony). Typ: R + D ([bloki.md](bloki.md), „Typy bloków"); blok ramy: [bloki.md](bloki.md), [bfdf6a]; menu, mega-panel, blok „Branże", menu mobile: [nawigacja.md](nawigacja.md), „Header i menu"; przełącznik języka: [wielojezycznosc.md](wielojezycznosc.md), [7d2mfu]; sekcja `naglowek-serwisu`: [sekcje.md](sekcje.md), [2ysenk].

## Gdzie

- **[dnkp95]** Wyłącznie w sekcji `naglowek-serwisu` (część szablonu `naglowek`): poza wstawiaczem, bez zapisu jako blok wielokrotnego użytku ([bloki.md](bloki.md), [ecp7bd]), bez wyrównania; edycja — [bloki.md](bloki.md), [bfdf6a].

## Pola

| ID | Pole | Atrybut | Rodzaj | Dozwolone | Limit | Wymagane / domyślne |
|---|---|---|---|---|---|---|
| **[szw6as]** | Linki pomocnicze (wiersz górny desktop, dół menu mobile) | `linki` | panel „Linki pomocnicze" (rozwinięty): lista etykieta + link ([bloki.md](bloki.md), [9s9332], [4svhm3], [wawuac]) | wpis serwisu albo adres | — | pusta; pozycja bez etykiety pominięta; link z ID — adres tłumaczenia |
| **[8um2q8]** | Przycisk (np. „E-learning") | `przycisk`: `etykieta`, adres | panel „Przycisk": pole „Etykieta" i kontrolka linku | wpis serwisu albo adres | — | pusty — bez etykiety przycisku nie ma; niska odmiana przycisku drugorzędnego |
| **[t3etq2]** | Link „Sprawdź całą ofertę" (mega-panel) | `linkOferty` | panel „Link „Sprawdź całą ofertę"": kontrolka linku, podpowiedź „Pusty = strona kategorii otwartego panelu." | wpis serwisu albo adres | — | pusty — strona kategorii otwartego panelu |
| **[qtgmdh]** | Blok „Branże" w panelu menu | `branzeWlaczone` | przełącznik „Pokaż blok „Branże"" (panel „Branże w panelu menu") | — | — | włączone |

## Warianty

- **[w3twdk]** Tryb wg typu strony (atrybut `data-przewijanie` na `<header class="naglowek">`, rozpoznanie `is_front_page()`): strona główna — `glowna` (na samej górze ciemny, klasa `tlo-ciemne`); pozostałe strony — `stala`: zawsze jasny i przyklejony (sam CSS), menu rozwinięte jasne. Wariant ciemny wyłącznie na górze strony głównej.
- **[5v96qh]** Stan zwinięty i rozwinięty: na desktopie rozwinięta pozycja menu głównego, na mobile hamburger zmienia się w X.

## Dane

- **[ns2kvd]** Skład: wiersz górny (logo, linki pomocnicze, przycisk) i wiersz menu głównego; mobile — belka z logo i hamburgerem. Logo (desktop i mobile) — link do strony głównej z `aria-label` „Feuer — strona główna" (i18n); nawigacje z etykietami dostępności „Linki pomocnicze", „Menu główne" (desktop i mobile).
- **[pdk4cc]** Strona główna (moduł `feuer-naglowek-przewijanie`, aktywny tylko przy `glowna`): na samej górze header ciemny, nieprzyklejony — półprzezroczysta maska na zdjęciu hero, odjeżdża z treścią; po wyjechaniu z ekranu przechodzi bez animacji w stan schowany (animacja migałaby jasnym headerem); po ruchu w górę o 24 px (ruch zsumowany w bieżącym kierunku) wysuwa się jasny i przyklejony (400 ms), po ruchu w dół — chowa się. Stan liczony od razu po załadowaniu wg bieżącego przewinięcia.
- **[3ytjba]** Strefa górna (przewinięcie mniejsze niż dolna krawędź miejsca headera w toku strony — nad nim może stać belka zapowiedzi): przyklejony header zawsze pokazany i stopniowo przechodzi w ciemny w drodze na samą górę.
- **[rwa934]** Otwarte menu (mega-panel, menu mobile, lista języków — element headera z `aria-expanded="true"`) wstrzymuje zmianę stanu headera.
- **[5b2w5m]** Przykleja się cały header (desktop — oba wiersze, mobile — belka); menu działa z przyklejonego headera w jego bieżącym wariancie. Kotwice (spis treści, „Do góry") zatrzymują się pod przyklejonym headerem (`scroll-padding-top` = wysokość headera). Przyklejony header staje pod paskiem administratora od 601 px (poniżej pasek nie jest przyklejony).

## Edytor

- **[akexrk]** W kanwie nieinteraktywny podgląd (`ServerSideRender` metodą POST w `Disabled`); edycja — [bloki.md](bloki.md), [bfdf6a].

## Wielojęzyczność

- **[vdcngx]** Sekcja `naglowek-serwisu` — jedna dla wszystkich języków (typ `sekcja` nietłumaczony: [sekcje.md](sekcje.md), [8bcbuy]): linki i przycisk wspólne; linki wskazane wpisem — [bloki.md](bloki.md), [a4xc8h]; menu z drzewa oferty — taksonomia nietłumaczona ([nawigacja.md](nawigacja.md), [3sxrwm]).

## Przykład

```html
<!-- wp:feuer/naglowek {"linki":[{"etykieta":"Baza wiedzy","url":"#"},{"etykieta":"O firmie","url":"#"},{"etykieta":"Kontakt","url":"#"}],"przycisk":{"etykieta":"E-learning","url":"#"},"lock":{"move":true,"remove":true}} /-->
```
