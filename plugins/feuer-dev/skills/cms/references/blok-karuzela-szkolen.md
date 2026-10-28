# feuer/karuzela-szkolen

„Karuzela szkoleń na zdjęciu" — sekcja na jednym zdjęciu tła (osobne zdjęcie na telefon): nagłówek, lead, link i karuzela kart szkoleń z danych — najbliższe terminy albo produkty „TOP 20". Typ: D ([bloki.md](bloki.md), „Typy bloków"). Źródło terminów: [bloki.md](bloki.md), [g93eyy]; najbliższy oznaczony miesiąc i losowanie: [bloki.md](bloki.md), [m5z6sd], [j9x79h]; tag produktu: [strony-zbiorcze.md](strony-zbiorcze.md), [vjmjws]; termin w adresie strony produktu: formularz-kontaktu.md, [utzf8f].

## Gdzie

- **[pyd9e9]** Samodzielna sekcja w treści stron (praktycznie tylko strona główna), bez ograniczenia liczby; osobny komponent — nie odmiana hero ani Kart informacyjnych.

## Pola

| ID | Pole | Atrybut | Rodzaj | Dozwolone | Limit | Wymagane / domyślne |
|---|---|---|---|---|---|---|
| **[jdw88w]** | Odmiana | `odmiana` | panel „Ustawienia": „Odmiana (do zdjęcia)" — pomoc „Jasna: tekst ciemny, karta bieżąca czerwona. Ciemna: tekst biały, karta bieżąca ciemna." | `jasna`, `ciemna` — wybór ręczny, wg jasności zdjęcia | — | `jasna` |
| **[cnhby8]** | Zdjęcie, Zdjęcie mobile (dekoracyjne, alt pusty) | `zdjecie`, `zdjecieMobile` (ID) | medium — toolbar bloku: „Zdjęcie", „Zdjęcie mobile" | obrazy z biblioteki mediów | — | obowiązkowe — niewybrane, usunięte albo nie obraz: obraz zastępczy |
| **[v7pmmp]** | Nagłówek (H2) | `tytul` | tekst z łamaniem wiersza, w miejscu | „Akcent w nagłówkach" ([bloki.md](bloki.md), [s56shy]); na froncie `wp_kses_post` | — | obowiązkowe |
| **[8scfz5]** | Lead | `lead` | tekst, w miejscu, podpowiedź „Lead (opcjonalny)…" | link | — | opcjonalne — pusty się nie wyświetla (link stoi wtedy pod nagłówkiem) |
| **[m23ynh]** | Link (pod leadem, link akcji A43 ze strzałką) | `link`: `etykieta`, `url`, `id` | etykieta — tekst jednowierszowy w miejscu (podpowiedź „Link (opcjonalny)…"); adres — przycisk z ikoną łącza w toolbarze (wciśnięty przy ustawionym adresie) | etykieta bez formatów | — | opcjonalne — bez etykiety linku nie ma; etykieta bez adresu: `<wprowadź link>` w miejscu tekstu, bez strzałki |
| **[ybw35q]** | Tekst przycisku kart — jedno pole dla wszystkich kart ([bloki.md](bloki.md), [5tj3aw]) | `przycisk` | tekst jednowierszowy, w miejscu (na dowolnej karcie) | bez formatów (na froncie bez znaczników) | — | pusty — „Zarezerwuj" (i18n) |
| **[e3ts8k]** | Źródło kart | `zrodlo` | panel: „Źródło kart" — „Terminy szkoleń", „TOP 20" (pomoc opisuje wybrane źródło) | `terminy`, `top-20` | — | `terminy` |
| **[6dwpn8]** | Szkolenia (tylko źródło „Terminy szkoleń") | `oferta` (ID kategorii) | lista „Szkolenia": „Wszystkie szkolenia" i kategorie oferty z wcięciami; pomoc „Kategoria obejmuje też swoje podkategorie." | — | — | 0 — wszystkie szkolenia |
| **[9yvuqs]** | Liczba kart | `limit` | lista: „Wszystkie" (0), 1–12; zmiana źródła ustawia domyślną liczbę źródła (TOP 20 — wszystkie, terminy — 12) | 0–12 (render przycina do zakresu) | — | 12 w `block.json` (niezależnie od źródła) |
| **[xnghng]** | Autoplay, Sekundy na kartę | `autoplay`, `sekundy` | przełącznik „Autoplay" (pomoc „Karty przewijają się same; najechanie kursorem i ręczna zmiana wstrzymują na 15 s."); pole „Sekundy na kartę" — tylko przy włączonym autoplayu (pusty, zerowy albo nienumeryczny wpis daje 3; ujemny — 1; ułamek obcinany do części całkowitej) | sekundy ≥ 1 | — | wyłączony; 3 s |
| **[2esewm]** | Szerokość zdjęcia w tle | `szerokoscTla` | panel „Ustawienia" — wspólne ustawienie bloków ze zdjęciem-tłem: css.md, [k34pyh] | `1440`, `1920` | — | `1440` |

## Dane

- **[wxrfcv]** Źródło „Terminy szkoleń" — źródło kart terminów ([bloki.md](bloki.md), [g93eyy]).
- **[hy5g3a]** Źródło „TOP 20": jedna karta = jeden opublikowany produkt (szkolenie albo usługa) z oznaczeniem „TOP 20"; trzy grupy — z aktualnym terminem (po dacie), z oznaczonym miesiącem (od najbliższego), „Termin do uzgodnienia" (losowo w przeglądarce, sekcja z `data-losuj` = limit); limit stosowany po ułożeniu (także w edytorze ta sama kolejność). Flaga „Nie pokazuj w listingu kategorii" — [produkt.md](produkt.md), [999uaf].
- **[2y7xxu]** Karta: badge (tag produktu — tylko gdy ustawiony), data, nazwa na karcie ([produkt.md](produkt.md), [hh6g67]), przycisk. Data zawsze obecna: termin („j F Y", strefa czasowa witryny, `<time datetime>`), przy TOP 20 bez terminu — najbliższy oznaczony miesiąc (`<time datetime="Y-m">`), bez miesiąca — „Termin do uzgodnienia" (`<span>` z tą samą klasą, i18n).
- **[9kvvym]** Przycisk karty — link do strony produktu; karta z aktualnym terminem dokłada `?termin=<id terminu>` (termin wybrany w Top visualu produktowym); `aria-label` „<tekst przycisku>: <nazwa>, <data albo miesiąc albo Termin do uzgodnienia>".
- **[3fa8gh]** Zdjęcia: oba ustawione — jedno `<picture>` (zdjęcie mobile jako źródło dla telefonu); brak któregoś — dwie warstwy (desktop i mobile), w miejscu brakującego obraz zastępczy. Odmiana ciemna: klasa sekcji `karuzela-szkolen-ciemna`, napis z klasą `tlo-ciemne` od 640 px (szerokość okna).
- **[tvqj5y]** Karuzela (Swiper, `view.js`): pierwsza karta bieżąca już w HTML; pętla od 5 kart (po losowaniu i przycięciu; architektura-kodu.md, [ucuuk5]), przy pętli poprzednia karta po lewej od startu (`loopFix`); bez pętli przy więcej niż jednej karcie za ostatnią — pusty slajd-wypełniacz (`aria-hidden`), żeby każda karta mogła stanąć przy lewej krawędzi.
- **[2xfs2c]** Zmiana karty bieżącej: przeciągnięcie, kreski (jedna na kartę, klikalne — najkrótszą drogą; tylko mysz i dotyk), klik w wąską kartę (bieżącą staje się kliknięta), przewijanie poziome (kółko, trackpad: jeden gest = jedna karta; gest — strumień zdarzeń `wheel` bez przerwy dłuższej niż 250 ms; własny nasłuch zamiast modułu Swipera). Skok o kilka kart — jeden płynny ruch z kroków (pierwszy ease-in, środkowe liniowo, ostatni ease-out). Najechanie na kartę — tytuł zmienia kolor (karta szara — kolor marki; karta bieżąca czerwona albo ciemna — kolor stanu hover tła), przycisk w stanie hover.
- **[xnryu8]** Autoplay (`data-autoplay` z liczbą sekund): przełącza karty co `sekundy`; wstrzymuje się na 15 s po najechaniu kursorem na sekcję (od zjechania) i po ręcznej zmianie karty; bez przycisku pauzy, bez obsługi `prefers-reduced-motion`.

## Edytor

- **[wxc8ve]** Lustrzany markup z edycją tekstów w miejscu; karty statyczne, w stanie startowym (pierwsza bieżąca, pozostałe wąskie), bez Swipera i bez kresek (pusty znacznik); linki kart w podglądzie — [bloki.md](bloki.md), [ap7hv3]. Odmiana ciemna dokłada `tlo-ciemne` wg szerokości okna kanwy (podgląd mobile jak front).
- **[wccjvj]** Brak kart — pas z komunikatem: TOP 20 — „Brak produktów z oznaczeniem „TOP 20" — na stronie blok się nie wyświetla.", terminy — „Brak aktualnych terminów w wybranym źródle — na stronie blok się nie wyświetla."; panel: „Źródło kart", „Szkolenia" (tylko przy terminach), „Liczba kart".

## Przykład

```html
<!-- wp:feuer/karuzela-szkolen {"zdjecie":86,"zdjecieMobile":87,"tytul":"Lepiej być tysiąc razy ostrożnym\u003cbr\u003e\u003cspan class=\u0022akcent\u0022\u003eniż raz się oparzyć.\u003c/span\u003e","lead":"Najbliższe terminy szkoleń otwartych.","link":{"etykieta":"Sprawdź całą ofertę szkoleń","url":"https://feuer.pl/oferta/szkolenia-podstawowe/"}} /-->

<!-- wp:feuer/karuzela-szkolen {"odmiana":"ciemna","zdjecie":88,"zdjecieMobile":89,"lead":"Szkolenia stacjonarne i online prowadzone przez praktyków.","przycisk":"Zapisz się","oferta":11,"limit":6,"autoplay":true} /-->

<!-- wp:feuer/karuzela-szkolen {"odmiana":"ciemna","zdjecie":88,"zdjecieMobile":89,"zrodlo":"top-20","limit":0} /-->
```
