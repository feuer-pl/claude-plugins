# Produkt

Typ wpisu `produkt` — produkty oferty: szkolenia i usługi. Pola, słowniki, metaboks „Dane produktu", synchronizacja między tłumaczeniami. Przegląd modelu: [model-tresci.md](model-tresci.md); taksonomie produktu: [taksonomie.md](taksonomie.md); artykuły: [artykuly.md](artykuly.md).

## Typ wpisu

- **[twdcn3]** Jeden typ `produkt` obejmuje wszystkie produkty oferty — szkolenia i usługi; rozróżnia je pole „Rodzaj".
- **[jtqdhk]** Typ publiczny (strona produktu na froncie), dostępny w REST (`/wp/v2/produkt/`, z meta produktu) i w edytorze blokowym; niehierarchiczny, bez archiwum typu; w panelu menu „Produkty".
- **[vdbftd]** Edycja obejmuje tytuł, treść (bloki), obrazek wyróżniający i pola własne; bez zajawki i autora.
- **[ta2mt2]** Taksonomie produktu: `oferta`, `branza`, `grupa`, `oznaczenie` ([taksonomie.md](taksonomie.md)).
- **[rndahr]** Treść strony produktu (tekst marketingowy) to bloki w edytorze wpisu (zestaw bloków: [uprawnienia.md](uprawnienia.md), [tpzesj]); meta produktu — wyłącznie dane strukturalne, nie tekst marketingowy; część z nich zasila bloki i listingi (sekcja „Odbiorcy").
- **[jd5bdw]** Szkolenie = produkt z rodzajem „szkolenie"; każdy inny produkt, także bez rodzaju, jest traktowany jak usługa (teksty i przyciski strony produktu, karty, Kalendarium).
- **[etsegv]** Produkt nie ma pola ani taksonomii podziału narracyjnego (filary z arkusza taksonomii); karty narracyjne strony głównej to treść bloku.
- **[9bzsa7]** Pola produktu to natywne post meta (klucze `_feuer_*`), bez ACF; jedna definicja (`feuer_meta_produktu()`) daje schemat REST, reguły czyszczenia i flagę synchronizacji między tłumaczeniami.

## Pola

| ID | Pole | Klucz | Typ i wartości | Dozwolone | Wymagane / domyślne | Uwagi |
|---|---|---|---|---|---|---|
| **[tpt5xf]** | Rodzaj | `_feuer_rodzaj` | kod: `szkolenie` (Szkolenie), `usluga` (Usługa) | wybór | domyślnie pusty (bez rodzaju) | pierwsze pole metaboksu |
| **[yhavp5]** | Nazwa skrócona | `_feuer_nazwa_skrocona` | tekst | tekst jednowierszowy, bez formatów | pusta = tytuł wpisu | bez limitu długości |
| **[ek2fr9]** | Opis na karcie | `_feuer_opis_karty` | tekst | tekst jednowierszowy, bez formatów | obowiązkowe | miękki limit 80 znaków |
| **[y6rd8s]** | Kluczowe informacje | `_feuer_kluczowe` | lista grup: `nazwa` (nazwa zakładki) i `wiersze` — lista par `etykieta`, `wartosc` | nazwa grupy i etykieta — tekst jednowierszowy, bez formatów; wartość — tekst z łamaniem wiersza: akapity, lista punktowana i numerowana, pogrubienie, kursywa, podkreślenie, przekreślenie, link | pusta lista | tylko szkolenie; bez stałego zbioru pól — każde szkolenie ma własne wiersze; szkolenie bez zakładek — jedna grupa bez nazwy |
| **[779j8w]** | Warianty | `_feuer_warianty` | lista nazw | tekst jednowierszowy, bez formatów | pusta lista | tylko szkolenie; same nazwy do pola wyboru wariantu, różnice między wariantami — w treści szkolenia |
| **[vvvvng]** | Terminy | `_feuer_terminy` | lista terminów: `id` (stały identyfikator), `data` (RRRR-MM-DD), `forma` (kod słownika „Forma" albo pusty), `opis` | data — pole daty; forma — wybór; opis — tekst jednowierszowy, bez formatów | pusta lista; termin bez daty odpada | tylko szkolenie; terminy jednego szkolenia mogą mieć różne formy; godziny i cena — w opisie terminu |
| **[m2vmwe]** | Powiązane produkty | `_feuer_powiazane` | lista ID produktów | wybór (wyszukiwanie) | pusta lista | bez limitu liczby; produkty dowolnego rodzaju i kategorii |
| **[btfbrf]** | Forma | `_feuer_forma` | lista kodów: `stacjonarne` (Stacjonarne), `e-learning` (E-learning), `webinar-otwarty` (Webinar otwarty), `webinar-zamkniety` (Webinar zamknięty) | wybór wielokrotny | pusta lista | tylko szkolenie; ten sam słownik dla formy terminu |
| **[r7h8yk]** | Egzamin/Certyfikat | `_feuer_egzamin` | tak / nie | przełącznik | nie | tylko szkolenie |
| **[v6ybtv]** | Poziom | `_feuer_poziom` | kod: `podstawowe` (Podstawowe/Wymagane), `doskonalace` (Doskonalące/Uzupełniające) | wybór | pusty („— brak —") | |
| **[gk23ct]** | Nowość | `_feuer_nowosc` | tak / nie | przełącznik | nie | niezależne od tagu |
| **[7e72f6]** | Promocja | `_feuer_promocja` | tak / nie | przełącznik | nie | |
| **[d7kf3f]** | Tag | `_feuer_tag` | kod: `wymagane-prawem` (Wymagane prawem), `nowosc` (Nowość), `zmiana-przepisow` (Zmiana przepisów), `wazne-teraz` (Ważne teraz) | wybór | pusty („Brak") | jeden na produkt; niezależny od pól Nowość i Promocja |
| **[zg23ht]** | Nie pokazuj w listingu kategorii | `_feuer_bez_listingu` | tak / nie | przełącznik | nie | |
| **[63cghg]** | Ranga | `_feuer_ranga` | tekst `1`–`5` (1 — najwyższa) | pole liczbowe 1–5 | pusta | zapis jako tekst: pusta wartość liczbowa w REST byłaby 0; REST przyjmuje wyłącznie tekst |
| **[xnggtp]** | Metadane | `_feuer_metadane` | tekst: frazy po przecinku | tekst jednowierszowy, bez formatów | pusty | |
| **[7zham2]** | Link do Moodle | `_feuer_moodle` | adres URL (http, https) | pole adresu | pusty | kurs e-learningowy na zewnętrznej platformie |
| **[zyzxke]** | Powiązany artykuł | `_feuer_artykul` | ID wpisu `post`; 0 = brak | wybór (wyszukiwanie) | 0 | |

- **[z3azb6]** Słowniki (rodzaj, forma, poziom, tag) istnieją wyłącznie w kodzie (`feuer_slowniki()`); meta przechowuje kod, a etykieta pochodzi ze słownika przez i18n.
- **[g9q4dq]** Zapis z REST i z metaboksu przechodzi przez te same reguły czyszczenia (callback zarejestrowany z meta).
- **[y32hrr]** REST odrzuca (400) wartość niezgodną ze schematem: kod spoza słownika, datę terminu spoza formatu RRRR-MM-DD, rangę podaną jako liczbę.
- **[wypu4b]** Czyszczenie przy zapisie: tak / nie — napisy „false" i „0" to fałsz; liczba — wartość bezwzględna, napis nieliczbowy daje 0; tekst — bez HTML, nieskalarny daje pusty tekst.
- **[n64v3g]** Podziały wierszy w tekście meta są zapisywane jako `\n` (formularz wysyła `\r\n`, REST `\n`).
- **[xhbays]** Kod spoza słownika i tekst niezgodny ze wzorcem schematu (np. data terminu) zapisują się jako pusty tekst; obiekt — tylko pola ze schematu, brakujące puste; z listy odpadają pozycje puste (wszystkie pola puste, „0" albo 0), pozostałe numerowane od nowa.
- **[nvcna7]** Terminy przy zapisie: termin bez daty odpada; `id` — istniejący czyszczony do małych liter, cyfr, `_` i `-`, pusty zastępowany nowym UUID; terminy posortowane rosnąco wg daty. Istnienie dnia w kalendarzu nie jest sprawdzane.
- **[htaspz]** Wartość wiersza kluczowych informacji — HTML z białą listą: `p`, `br`, `strong`, `em`, `del`, `span` (wyłącznie styl `text-decoration: underline;`, inne style usuwane), `a` (`href`, `target`, `rel`), `ul`, `ol`, `li`; inne znaczniki usuwane z zachowaniem treści. Zapis jak treść edytora klasycznego (akapity jako puste wiersze, na froncie `wpautop()`), przycięty z białych znaków; wartości zapisane zwykłym tekstem działają bez zmian.
- **[nahg3y]** Link do Moodle: adres z innym schematem niż http / https zapisuje się jako pusty, adres bez schematu dostaje `http://`.
- **[d7jm2p]** Powiązany artykuł: ID wpisu innego typu niż `post` zapisuje się jako 0; artykuł w dowolnym statusie.
- **[h53cz5]** Meta nieobecne w bazie ma wartość domyślną wg typu: lista — pusta, tak / nie — fałsz, liczba — 0, tekst — pusty.
- **[6jdg7v]** Produkt ma też pola SEO — „Tytuł dla wyszukiwarek" (`_feuer_seo_tytul`) i „Opis dla wyszukiwarek" (`_feuer_seo_opis`): [seo.md](seo.md), „Pola nadpisania".

## Relacje

- **[n7xjen]** Powiązane produkty: produkt wskazuje inne produkty ręcznie (lista ID), wyborem spośród wszystkich produktów, bez ograniczenia do rodzaju i kategorii.
- **[mabnc5]** Produkt → artykuł (`_feuer_artykul`): powiązanie jednokierunkowe — artykuł nie przechowuje produktu. Powiązanym artykułem jest artykuł z dokumentu głównego produktu. Produkt artykułu (strona artykułu): [artykuly.md](artykuly.md).

## Edycja i uprawnienia

- **[fn6cc9]** Pola produktu — jeden metaboks „Dane produktu" w głównej kolumnie edytora, pod treścią, nad innymi metaboksami; kolejność pól — jak wiersze tabeli „Pola" (na górze Rodzaj, Nazwa skrócona, Opis na karcie; dalej sekcje Kluczowe informacje, Warianty, Terminy, Powiązane produkty, Parametry). Taksonomie — panele boczne edytora: natywne (kategoria oferty, branże, grupy) i własna lista pól wyboru Oznaczeń ([taksonomie.md](taksonomie.md), [sa7hx9]). Wygląd standardowy WordPressa.
- **[ecz3g8]** W edytorze blokowym metaboks leży w dolnym panelu „Metaboksy": u konta, które go jeszcze nie rozwijało, panel jest zwinięty do paska na dole edytora. Kliknięcie paska rozwija panel i zwija go; stan zapamiętują preferencje edytora konta.
- **[djcwzm]** Nowe pole produktu — wpis w `feuer_meta_produktu()`: `'_feuer_<nazwa>' => array( 'schemat' => <schemat REST>, 'synchronizacja' => <tak / nie> )`; kod ze słownika — `$kod( '<słownik>' )`, słownik — klucz w `feuer_slowniki()`. Z wpisu powstają schemat REST, czyszczenie wartości i synchronizacja tłumaczeń.
- **[bwfbje]** Pole w metaboksie dopisuje się osobno: wiersz w `$wiersze` funkcji `feuer_produkt_metaboks_tresc()`; element formularza z nazwą `feuer[<klucz>]` (lista — `feuer[<klucz>][]`) — zapis czyta wyłącznie te pola ([dyzwxw]).
- **[ntvevk]** Pole w operacjach obsługi z czatu dopisuje się osobno: cms-z-czatu.md, [hkzgdn].
- **[3utknd]** Sekcje Kluczowe informacje, Warianty, Terminy i parametry Forma, Egzamin/Certyfikat są widoczne tylko dla rodzaju „szkolenie"; zmiana pola „Rodzaj" przełącza je od razu, bez przeładowania. Ukryte pola zostają w formularzu — ich dane zapisują się bez zmian.
- **[afqf86]** Pole wyboru ze słownika ma pustą opcję = brak wartości; pozostałe opcje w kolejności słownika.
- **[7nfwh7]** Listy (grupy i wiersze kluczowych informacji, warianty, terminy, powiązane produkty): „Usuń" przy wierszu usuwa go od razu, bez potwierdzenia (usunięcie grupy — z jej wierszami); „Dodaj …" pod listą dodaje wiersz na końcu; kolejności nie da się zmienić. Produkt bez kluczowych informacji pokazuje jedną pustą grupę; nowa grupa nie ma wierszy.
- **[qkpbby]** Wartość wiersza kluczowych informacji — edytor klasyczny WordPressa: jeden rząd przycisków (pogrubienie, kursywa, podkreślenie, przekreślenie, lista punktowana, lista numerowana, link), bez zakładki „Tekst" i bez mediów, wysokość wg treści; edytor dostaje także wiersz dodany przyciskiem.
- **[exa28p]** Terminy: wiersz = data (pole daty), forma (wybór z pustą opcją „— forma —"), opis (podpowiedź „Opis") i „Usuń"; ukryte pole `id` (puste dla nowego terminu) wraca w zapisie; nowy termin — „Dodaj termin".
- **[6shzg6]** Powiązane produkty: pole „Szukaj produktu…" z podpowiedziami przeglądarki — produkty w dowolnym statusie poza koszem, bez edytowanego, alfabetycznie, w języku edytowanego produktu. „Dodaj" (albo Enter) czyści pole i dodaje produkt o tytule wybranym z podpowiedzi; tekst spoza podpowiedzi i produkt już dodany — pole wyczyszczone, lista bez zmian. Produkt spoza podpowiedzi (kosz, inny język) jest pokazywany z tytułem swojego wpisu.
- **[fc42w7]** Powiązany artykuł: pole „Szukaj artykułu…" z podpowiedziami — wpisy `post` w dowolnym statusie poza koszem, alfabetycznie, w języku produktu; pole pokazuje tytuł powiązanego artykułu. Wybór z podpowiedzi ustawia ID; tekst spoza podpowiedzi (także pusty) = brak artykułu. Enter w polu nic nie robi.
- **[eukp8h]** Pole z limitem długości (Opis na karcie — 80 znaków): licznik i ostrzeżenie jak w blokach ([bloki.md](bloki.md), [m6bptd], [fg2k4y]); w metaboksie licznik przy aktywnym polu.
- **[3am4fq]** Opis na karcie — tekst sprzedażowy: co to jest i jak pomaga klientowi w pracy firmy i ludzi, z korzyścią; zwrot do klienta w 2. osobie liczby pojedynczej (np. „Wejdź na rynek z BHP gotowym od pierwszego dnia, bez ryzyka kar z PIP.").
- **[vnd48f]** Metaboks zapisuje tylko przy ważnym nonce formularza, poza autozapisem i dla użytkownika z prawem edycji wpisu — zapis przez REST, WP-CLI, szybka i masowa edycja listy nie przechodzą przez metaboks i niczego nie zerują.
- **[7t37mg]** Zapis metaboksu zapisuje naraz wszystkie meta produktu wartościami formularza; pole nieprzesłane (odznaczone pole wyboru, pusta lista) dostaje wartość domyślną.

## Odbiorcy

- **[hh6g67]** Karty produktu (listingi stron zbiorczych, Zobacz także, Karuzela szkoleń, Kalendarium) pokazują nazwę skróconą, a gdy pusta — tytuł wpisu; strona produktu (H1, okruszki) — tytuł wpisu.
- **[96rack]** Opis na karcie: karta produktu stron zbiorczych, Kalendarium, szablon artykułu.
- **[2khtq5]** Kluczowe informacje — blok „Kluczowe informacje" (tylko wyświetla).
- **[ja6sjh]** Warianty i terminy — Top visual produktowy ([README bloku](blok-top-produktowy.md), [jsxm7f]); pola usługi zostają w meta i są pomijane.
- **[d566w4]** Aktualne terminy = data późniejsza niż dzisiejsza (strefa czasowa witryny); dzisiejszy i przeszłe nie są pokazywane nigdzie w serwisie (bloki, listingi, wybór terminu).
- **[v446ku]** Termin w adresie strony szkolenia: `?termin=<id terminu>` — identyfikator wspólny dla tłumaczeń.
- **[srrv3u]** Powiązane produkty — blok „Zobacz także".
- **[wmnf4g]** Tag — badge na kartach (Kafle produktowe, Zobacz także, Karuzela szkoleń): odmiana, ikona i nazwa wg kodu — [strony-zbiorcze.md](strony-zbiorcze.md), [vjmjws].
- **[293tqa]** Nowość, Promocja i Ranga — kolejność produktów w listingach.
- **[999uaf]** Flaga „Nie pokazuj w listingu kategorii" wyłącza produkt ze wszystkich list automatycznych produktów i z nawigacji, także z kart Terminów i Karuzeli szkoleń (poza bieżącym szkoleniem w Terminach); artykułów powiązanych z produktem nie wyłącza ze źródeł Listy artykułów.
- **[hkxpca]** Metadane — wyszukiwarka katalogu.
- **[v2qktg]** Powiązany artykuł — link „Dowiedz się więcej" w Top visualu produktowym.
- **[ujbj5d]** Forma, Egzamin/Certyfikat, Poziom i Link do Moodle nie są wyświetlane na froncie (dostępne w REST).

## Wielojęzyczność

- **[hj5uc9]** Produkt jest tłumaczony przez Polylang — wersja językowa to osobny wpis.
- **[wv5rjc]** Synchronizowane między tłumaczeniami (wartości nietekstowe): Rodzaj, Terminy (data i forma), Powiązane produkty, Forma, Egzamin/Certyfikat, Poziom, Nowość, Promocja, Tag, Nie pokazuj w listingu kategorii, Link do Moodle (jeden kurs dla wszystkich języków), Ranga, Powiązany artykuł.
- **[dpyfes]** Tekst wolny żyje per tłumaczenie, bez synchronizacji: Nazwa skrócona, Opis na karcie, Kluczowe informacje, Warianty, Metadane, opis terminu.
- **[pyhqcb]** Terminy w tłumaczeniu: data i forma pochodzą z wersji zapisywanej (przy tworzeniu tłumaczenia — z oryginału), opis jest własny tłumaczenia, dopasowany po `id` terminu; termin dodany w wersji źródłowej trafia do tłumaczenia bez opisu.
- **[6ys9hz]** Powiązany artykuł — adres artykułu w języku strony: [wielojezycznosc.md](wielojezycznosc.md), [b8tb5u].
