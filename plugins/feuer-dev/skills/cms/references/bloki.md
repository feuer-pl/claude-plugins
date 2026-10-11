# Bloki

Bloki wtyczki `feuer-komponenty`: typy, reguły wspólne modelu edycji, zestawy formatów, mechanizmy wspólne i rejestr. Opis pojedynczego bloku — README bloku (link w rejestrze); paleta treści redakcyjnej: [paleta-tresci.md](paleta-tresci.md); wzorce stron: [wzorce-stron.md](wzorce-stron.md); sekcje: [sekcje.md](sekcje.md); bloki dostępne w edytorze i blokady: [uprawnienia.md](uprawnienia.md).

## Typy bloków

- **[3h2jzq]** T — treściowy: redaktor wpisuje treść w miejscu (pola tekstowe, bloki wewnętrzne); markup w edytorze lustrzany względem frontu.
- **[exsr92]** D — z danych: treść z CMS (meta wpisu, taksonomie, inne wpisy); redaktor konfiguruje blok, teksty bloku wpisuje w miejscu.
- **[22nx5c]** R — rama: blok w sekcji chronionej (`naglowek-serwisu`, `stopka-serwisu`; [sekcje.md](sekcje.md), [8vsg6f], [etwwzs]).
- **[nv2eze]** Szablonowy: blok w szablonie motywu, renderuje dane bieżącej strony (artykuł, strona kategorii, strona branży, strona Bazy wiedzy, okruszki, sekcja po slugu); w edytorze witryny — wyłącznie znacznik miejsca (treść znacznika — README bloku).
- **[v33y23]** Strony składają się z bloków firmowych (komponenty z projektu) i bloków palety ([paleta-tresci.md](paleta-tresci.md), [8psccg], [p69bw2]); ograniczenia typów bloków w treści wpisu nie ma ([uprawnienia.md](uprawnienia.md), [tpzesj]).
- **[h63tez]** Blok firmowy = komponent z projektu; redaktor zmienia jego atrybuty i bloki wewnętrzne (teksty, obrazy, wybór produktów i kategorii, zdefiniowane odmiany), bez ustawień kolorów, typografii i odstępów; w panelu „Zaawansowane" każdego bloku zostają pola „Dodatkowe klasy CSS" i „Dodatkowy CSS" (własny CSS bloku — dla użytkowników z `edit_css`, czyli z `unfiltered_html`: administrator i redaktor).
- **[68qxdh]** Mobile — te same bloki; różnice wyłącznie responsywne (CSS), bez osobnych bloków mobilnych; siatki i rzędy kart nie zamieniają się w karuzele — karuzelami są wyłącznie bloki karuzel, na każdej szerokości.

## Model edycji

### Teksty

- **[3g9tqb]** Każdy tekst widoczny w bloku — także nagłówek sekcji, lead, tekst przycisku i linku — redaktor wpisuje i zmienia w miejscu, w kanwie edytora; w bloku zaszyta jest wyłącznie logika, bez której blok nie działa.
- **[8464y5]** Wyjątek — etykiety interfejsu wspólne dla serwisu są zaszyte w kodzie (i18n), m.in.: menu („Branże", „Sprawdź całą ofertę"), stopka („Do góry", „Oferta"), szablon artykułu („Spis treści", teksty linku do produktu i CTA produktu), link „Wstecz" okruszków, pola wyboru Top visualu produktowego („Wybierz wariant", „Termin"), wyszukiwarka katalogu i stan pusty listy produktów kategorii, „Pozostałe" Listy artykułów, „Termin do uzgodnienia" kart TOP 20.
- **[w7etph]** Pusty tekst bloku — tekst domyślny przez i18n (nigdy `default` w `block.json`) albo znacznik pola obowiązkowego.
- **[49nkuy]** Wielojęzyczność bloku w treści wpisu: teksty pól i bloki wewnętrzne należą do treści wpisu, więc są per tłumaczenie wpisu; media (ID załącznika: zdjęcia, ikony, filmy) są wspólne dla języków i nie są rozwiązywane na tłumaczenie ([media.md](media.md), [mza4r8]); pusty tekst — tekst domyślny w języku strony ([w7etph]); link wskazany wpisem — adres tłumaczenia ([a4xc8h]); pozycje z danych — wpisy w bieżącym języku: listy automatyczne wyłącznie w języku strony ([wielojezycznosc.md](wielojezycznosc.md), [4htqwa]), ID wpisów i termów przez abstrakcję tłumaczeń ([kyvf24]); taksonomie nietłumaczone — [7n3mcs]. Odstępstwa — README bloku.
- **[taeeq4]** Krótkie teksty edytowane w miejscu z pogrubieniem, kursywą i łamaniem wiersza (link „Sprawdź więcej newsów" Aktualności, etykieta „Sprawdź także:", prawa autorskie w stopce) — `feuer_tekst_z_formatami()`: przepuszcza `strong`, `em`, `br` bez atrybutów, inne znaczniki usuwa z zachowaniem tekstu; tekst pusty po usunięciu znaczników i białych znaków (także twardych spacji) — tekst domyślny.
- **[5tj3aw]** Tekst przycisku na kartach z danych (Terminy, Karuzela szkoleń) — jedno pole bloku, wspólne dla wszystkich kart.
- **[c3atk4]** Treść, którą da się zapisać jako tekst formatowany i której kod nie dzieli na części (część podstawiana gdzie indziej — inny blok, zapytanie, dane strukturalne, prewypełnienie formularza), to jedno pole tekstu formatowanego, nie zestaw osobnych pól.
- **[rg4r9f]** Pole tekstu formatowanego — bloki wewnętrzne: akapity, lista punktowana i numerowana, formaty inline palety; wygląd wg [paleta-tresci.md](paleta-tresci.md), „Gdzie obowiązuje" ([zpunnt]).
- **[yjyym4]** Pola sprzed reguły tekstu formatowanego mają węższe zestawy formatów — zestaw pola: kolumna „Dozwolone" w README bloku.
- **[4qc97j]** Pole jednowierszowe blokuje łamanie wiersza.
- **[93sxaw]** Nagłówki w edytorze: H1 — tytuł wpisu albo pole H1 bloku otwierającego strony; poziomy nagłówków w treści — [paleta-tresci.md](paleta-tresci.md), [q2s8np].
- **[8rz9hk]** Pole tekstowe bloku firmowego ma własną listę dozwolonych formatów inline (`allowedFormats`): zestaw nazwany („Zestawy formatów") albo listę własną pola (README bloku).

### Pola obowiązkowe

- **[yekaze]** Puste pole obowiązkowe nie ukrywa bloku: w jego miejscu element zastępczy trudny do przeoczenia, na froncie i w edytorze; reguła dotyczy każdego pola obowiązkowego (mechanizm: `includes/rama.php`, `css/zdjecie-zastepcze.css`, `ikony/logo.svg`).
- **[5p6gwz]** Pole obowiązkowe = pole obecne we wszystkich widokach projektu; pole nieobecne w którymś widoku jest opcjonalne. Obowiązkowość pola — README bloku.
- **[wdhnxv]** Zdjęcie obowiązkowe niewybrane albo usunięte z biblioteki mediów — obraz zastępczy: logo Feuer na szarym tle, granice kadru widoczne (`feuer_zdjecie()`: obraz o ID w rozmiarze `full` albo podanym; brak — `span.zdjecie-zastepcze` bez atrybutów obrazu; styl `feuer-zdjecie-zastepcze` dołącza blok).
- **[myhuw8]** Puste pole tekstowe obowiązkowe — znacznik `<wprowadź dane>` (`feuer_pole_obowiazkowe()`); puste = nic po `trim` — pole z samym `<br>`, innym znacznikiem albo twardą spacją uchodzi za wypełnione. W edytorze puste pole obowiązkowe (`RichText`) pokazuje ten sam znacznik jako `placeholder`.
- **[c8b829]** Link obowiązkowy z tekstem, ale bez adresu — znacznik `<wprowadź link>` w miejscu tekstu (`feuer_link_obowiazkowy()`).
- **[4bzbk9]** Znaczniki pól obowiązkowych przechodzą przez i18n ([wielojezycznosc.md](wielojezycznosc.md), [v25q78]).
- **[aast68]** Puste pole obowiązkowe render bloku zgłasza akcją `feuer_pole_puste` z nazwą pola (parametr `$pole` funkcji `feuer_pole_obowiazkowe()`, `feuer_link_obowiazkowy()` — link z tekstem bez adresu, `feuer_zdjecie()`): atrybut bloku (link — atrybut linku), `tresc` — strefa treści (bloki wewnętrzne), `obrazek` — obrazek wyróżniający wpisu, `kluczowe` — pole produktu „Kluczowe informacje". Ze zgłoszeń powstaje lista niewypełnionych pól wpisu w obsłudze z czatu (cms-z-czatu.md, „Niewypełnione pola obowiązkowe").
- **[7b8txa]** Nazwę pola podaje się wyłącznie dla pól wpisu, w którym stoi blok; puste dane innego obiektu (inny produkt, term, sekcja) pokazują znacznik bez zgłoszenia. Nowe pole obowiązkowe bloku — wywołanie z nazwą pola.

### Limity długości

- **[m6bptd]** Limity długości pól są miękkie: licznik i ostrzeżenie w edytorze, bez blokady wpisywania.
- **[fg2k4y]** Licznik „N / limit" pod polem (dymek `Popover`, `bottom-end`) — wyłącznie przy aktywnym polu (kursor w polu); po przekroczeniu czerwony z nadmiarem („74 / 60 — za długie o 14"); markup kanwy bez zmian.
- **[cgbr82]** Liczą się znaki widoczne (tekst bez znaczników, ze spacjami); łamanie wiersza = 1 znak; formatowanie się nie liczy.
- **[8v54de]** Pole z limitem — komponent `PoleZLimitem` (`src/wspolne/limit.js`); parametr `identifier` = klucz atrybutu (po nim rozpoznawane jest aktywne pole).

### Pozycje

- **[4dtarj]** Bloki z rzędem pozycji (Dla kogo, Proces współpracy, Program, limit kart Terminów): liczba pozycji w toolbarze bloku — 2 / 3 / 4 / 6; 5 wyłącznie w „Dla kogo"; szablon bloków wewnętrznych zablokowany (bez dodawania i usuwania, przestawianie dozwolone).
- **[edg7dw]** Dla kogo, Proces współpracy, Program: po wstawieniu 4 pozycje; zmniejszenie liczby usuwa ostatnie pozycje z treścią (cofnięcie: Ctrl+Z, rewizje wpisu), zwiększenie dodaje puste pozycje na końcu.
- **[raemfr]** Bloki potomne (pozycja, krok, pytanie, karta, kolumna) — wyłącznie wewnątrz rodzica (`parent` w `block.json`).
- **[n7utms]** Strefa treści bloku — bloki wewnętrzne z listą dozwolonych bloków; kompozycja bloku (tło, nagłówek, CTA) zamknięta w jego atrybutach i strukturze.

### Dane i kontekst

- **[wvvavm]** Blok czerpie dane z kontekstu bieżącego wpisu (`usesContext`: `postId`, `postType` — np. bloki strony produktu) albo z atrybutu (wybór produktów, kategorii, źródła).
- **[s598n9]** Dane do lustrzanego markupu w edytorze liczy `render.php` bloku: żądanie POST `/wp/v2/block-renderer/<blok>` (`context=edit`, `post_id`, `feuer_dane=1`, atrybuty w treści żądania), odpowiedź — JSON w polu `rendered`; dodatkowe parametry dołączane do żądania (np. `feuer_przyklad` — podgląd we wstawiaczu).
- **[78v65a]** Hook danych (`src/wspolne/dane.js`): `undefined` w trakcie wczytywania, `null` przy błędzie; odświeżanie przy zmianie bloku, atrybutów, parametrów albo wpisu; spóźnione odpowiedzi poprzednich żądań ignorowane.
- **[6c3sys]** Pole wyszukiwarki w edytorze — HTML z `render.php`, nieaktywny (`inert`), bez własnego pudełka (`display: contents`): układ jak na froncie.

### Zachowania w edytorze

- **[8ve2eb]** Zachowania JS (akordeon, zakładki, karuzele, menu, spis treści) działają wyłącznie na froncie (architektura-kodu.md, [janx9y]); w edytorze panele rozwinięte, wszystkie pozycje widoczne i edytowalne.
- **[8jw4ud]** Wyjątki: pozycje z danych nieedytowalne w kanwie (karuzele Karuzeli szkoleń i Zobacz także, zakładki tabeli Kluczowych informacji) — w edytorze stan startowy jak na froncie przy wczytaniu; Program w odmianie „Zakładki" — w edytorze widoczny panel zaznaczonego etapu, jak na froncie (README bloku).
- **[ywafc8]** Obowiązkowa strefa treści (bloki wewnętrzne) bez bloków: edytor wstawia z powrotem jeden pusty akapit z podpowiedzią `<wprowadź dane>` (atrybut `placeholder`); nowy blok startuje z jednym takim akapitem. Wyjątki i dodatki — README bloku.
- **[ap7hv3]** Linki w podglądzie bloku w edytorze (pozycje renderowane po stronie serwera, karty, kafle, stopka) są nieaktywne — klik nie przenosi kanwy na inną stronę.
- **[jtnzgj]** Strzałka przycisku (atom A41, rysowana przez `::after`) pojawia się w kanwie edytora dopiero po wpisaniu tekstu etykiety — podpowiedź pustego pola RichText też korzysta z `::after`; podkreślenie etykiety kategorii (`.etykieta-kategorii`) jest również `::after`, dlatego pole etykiety stoi w wewnętrznym `span`.
- **[pufx5c]** W `button` i `a` nie da się wygodnie edytować tekstu RichText — w kanwie edytora tekst przycisku i linku stoi w elemencie `span` (kafel-przycisk — w `div`).

### Bloki ramy i szablonowe

- **[89q53x]** Bloki ramy i szablonowe (`feuer/naglowek`, `feuer/stopka`, `feuer/okruszki`, `feuer/sekcja`, `feuer/artykul`, `feuer/kategoria`, `feuer/branza`, `feuer/baza-wiedzy`) są ukryte we wstawiaczu (`inserter: false`).
- **[bfdf6a]** Header i stopka to zamknięte bloki ramy: administrator redaguje w sekcji wyłącznie ich atrybuty (panel boczny), struktura jest zaszyta w bloku; szczegóły edycji i podglądu — README bloków ([naglowek](blok-naglowek.md), [stopka](blok-stopka.md)).

## Zestawy formatów

Zestaw = lista formatów inline pola tekstowego bloku (`allowedFormats`). Pole bloku firmowego ma zestaw nazwany (niżej) albo listę własną — w README bloku.

| ID | Zestaw | Formaty | Kod |
|---|---|---|---|
| **[s56shy]** | „Akcent w nagłówkach" | akcent (`feuer/akcent`, `span.akcent` — ExtraBold), kolor marki (`feuer/akcent-marki`, `span.akcent-marki`), kursywa, podkreślenie | `FORMATY_AKCENTU` |
| **[bmw7u4]** | „Akcent w nagłówkach — bez akcentu" (pola w całości ExtraBold) | kolor marki, kursywa, podkreślenie | `FORMATY_BEZ_AKCENTU` |
| **[nj47ej]** | „Paleta" | formaty inline palety ([paleta-tresci.md](paleta-tresci.md), [7wwnuc]) | bloki core palety, bez `allowedFormats` |
| **[nmwmdu]** | „Krótki tekst" | pogrubienie, kursywa, łamanie wiersza | `feuer_tekst_z_formatami()` |
| **[9xgmea]** | bez formatów | — | `allowedFormats` pusta |

- **[nwcsbu]** Formaty „Akcent", „Kolor marki" i akcent H1 Top visualu kontentowego (`feuer/tytul-duzy`, `span.tytul-duzy` — słowo większe; poza zestawami) rejestruje `src/wspolne/akcent.js` — raz, mimo importu w wielu blokach; dostępność w blokach core — [paleta-tresci.md](paleta-tresci.md), [7wwnuc], [ve4jan].
- **[mdu3cy]** Format „Akcent" zmienia wygląd wyłącznie w polu lżejszym niż ExtraBold: w nagłówkach w całości ExtraBold (Terminy i ich stan pusty, Sekcja kontaktowa, Karty informacyjne w zwykłej odmianie) przycisk „Akcent" jest dostępny, ale nic nie zmienia — wyróżniają kolor marki, kursywa i podkreślenie.

## Linki i pola panelu

- **[wawuac]** Kontrolka linku (`LinkControl`) zapisuje adres, a dla wpisu serwisu także jego ID; bez dodatkowych ustawień (np. otwarcie w nowej karcie); usunięcie linku zeruje adres i ID.
- **[a4xc8h]** Link z ID → adres tłumaczenia wpisu w bieżącym języku (abstrakcja tłumaczeń, `feuer_adres_linku()`), niezależnie od statusu wpisu (także szkic i kosz); wpis nie istnieje albo link bez ID — zapisany URL; brak obu — pusty adres.
- **[9s9332]** Lista linków w panelu bocznym: pozycja = pole „Etykieta" + pole linku; na froncie elementy `<a>` (szablon bloku), etykieta jako tekst; pozycja z pustą etykietą (także „0") pominięta; z etykietą bez adresu — link z pustym `href`, bez znacznika `<wprowadź link>`.
- **[4svhm3]** Lista pozycji w panelu bocznym: przy pozycji „Wyżej" (nieaktywny przy pierwszej), „Niżej" (nieaktywny przy ostatniej), „Usuń" — przesunięcie zamienia pozycję z sąsiednią; „Dodaj pozycję" dopisuje pustą na końcu; bez limitu liczby.
- **[4arnn9]** Pole obrazu w panelu: wyłącznie obrazy z biblioteki mediów, dla użytkowników z prawem wgrywania; przycisk „Wybierz obraz", po wyborze „Zmień obraz".

## Źródła pozycji

- **[fn4snx]** Blok z listą pozycji wybiera w ustawieniach jedno źródło spośród udostępnionych przez blok: wybór ręczny, taksonomia (kategoria oferty z potomkami, branża) albo filtr predefiniowany z kodu (np. „TOP 20", miesiące). Wybór źródła mają: Kafle produktowe, Kafle kategorii, Lista artykułów, Zobacz także, Karuzela szkoleń, Terminy (źródła — README bloku).
- **[fejddw]** Jedno źródło, bez wyboru: Kalendarium, Aktualności (4 najnowsze artykuły), Kafelki branż (wszystkie branże); Kafle produktowe w sekcji branży mają źródło „branża bieżącej strony" ([sekcje.md](sekcje.md), [8h54zx]), Lista artykułów na stronie Bazy wiedzy — wszystkie artykuły.
- **[x7a42s]** Wybór ręczny pozycji jest wspólny dla bloków (Zobacz także, Kafle produktowe, Lista artykułów — typ `post`): render `feuer_produkty_wybrane()`, dane panelu `feuer_wybor_produktow_panel()`, panel `src/wspolne/wybor-produktow.js`.
- **[86nqk3]** Render wyboru ręcznego: wyłącznie wpisy opublikowane wybieranego typu, rozwiązane przez abstrakcję tłumaczeń ([wielojezycznosc.md](wielojezycznosc.md), [bacp9q] — dziś przechodnia, pozycje nie odpadają), w kolejności listy redaktora; ID ≤ 0 pomijane; powtórzenia nie są usuwane (unikalność zapewnia panel).
- **[raee4t]** Panel wyboru ręcznego: pole z listą wybranych (kolejność kart, „Wyżej" / „Niżej" / „Usuń") i wyszukiwarka „Dodaj …" podpowiadająca nazwy z katalogu bez już wybranych; wybór dopisuje pozycję na końcu; przy limicie bloku — komunikat zamiast wyszukiwarki („Maksymalnie %d produktów.").
- **[ksamwa]** Etykieta wybranego wpisu w panelu: tytuł tłumaczenia w bieżącym języku ze stanem — „(szkic)" (także oczekujący i inny nieopublikowany), „(prywatny)", „(zaplanowany)", „(w koszu)", „(brak tłumaczenia)" (tytuł oryginału); ID bez wpisu albo wpis innego typu — „Wpis N (usunięty)".
- **[6g32r3]** Katalog wyszukiwania: wszystkie wpisy wybieranego typu poza koszem (także szkice, prywatne, zaplanowane), wyłącznie w języku strony, bez bieżącego wpisu, bez limitu, rosnąco po tytule; wyszukiwanie po nazwie także bez polskich znaków („lodz" → „Łódź"), najpierw nazwy zaczynające się od frazy.
- **[ck9xys]** Lista wyboru kategorii oferty (bloki wybierające kategorię): pozycja 0 „Wszystkie szkolenia" (opcjonalna) i termy `oferta` z wcięciem „— " na poziom drzewa (kolejność — [taksonomie.md](taksonomie.md), [xktvsv]), nazwy z encjami zdekodowanymi.
- **[g93eyy]** Źródło kart terminów (Terminy, Karuzela szkoleń; `feuer_szkolenia_z_oferty()`): opublikowane produkty rodzaju „szkolenie" bez flagi „Nie pokazuj w listingu kategorii" ([produkt.md](produkt.md), [999uaf]) — wszystkie albo z kategorii oferty (z podkategoriami); karta na każdy aktualny termin, najbliższe najpierw, przy tej samej dacie wg nazwy na karcie (porównanie bajtowe).
- **[xrqdvx]** Brak aktualnych terminów: Terminy (źródło inne niż bieżące szkolenie) i Karuzela szkoleń (źródło „terminy") — zachowanie jak przy braku pozycji ([szj5f5]).
- **[szj5f5]** Blok z danych bez pozycji do pokazania nie renderuje się na froncie (wyjątek: Kafelki branż — wyświetlają się z samym kaflem „Inna branża?", [README bloku](blok-kafelki-branz.md), [k6zrjp]); w edytorze w miejscu pozycji komunikat o braku, kończący się zdaniem „… Na stronie blok się nie wyświetla." (warunek „brak" i treść komunikatu — README bloku).
- **[m5z6sd]** Najbliższy oznaczony miesiąc produktu (Kalendarium, karty TOP 20 Karuzeli szkoleń): pierwszy miesiąc z jego oznaczeń od bieżącego włącznie, z przejściem przez koniec roku; produkt bez oznaczeń miesięcy go nie ma.
- **[j9x79h]** Losowa kolejność kart (karty „Termin do uzgodnienia" TOP 20 w Karuzeli szkoleń, produkty w obrębie miesiąca w Kalendarium) powstaje w przeglądarce (`src/wspolne/tasuj.js`, Fisher–Yates) — niezależnie od cache strony.

## Film zamiast zdjęcia

- **[9q8scd]** Top visual kontentowy, Belka informacyjna i Karty informacyjne na zdjęciu (także hero) mogą zamiast zdjęcia pokazać film: MP4 z biblioteki mediów w pętli, bez dźwięku; zdjęcie zostaje w bloku, niewidoczne, dopóki film istnieje. Mechanizm wspólny: `feuer_film()` (`includes/film.php`), moduł `feuer-film` (`js/film.js`), edytor `src/wspolne/film.js`.
- **[hcje6t]** „Film" (atrybut `film`) i „Film mobile" (`filmMobile`) w pasku narzędzi bloku — wyłącznie pliki `video/mp4`. Top visual kontentowy i Belka informacyjna: „Resetuj" (widoczny przy wybranym filmie) zeruje atrybut i wraca do zdjęcia, bez walidacji i ostrzeżeń; Karty informacyjne na zdjęciu — własny wybór kreacji bez „Resetuj", brak kreacji mobile — ostrzeżenie i blokada zapisu wpisu (README bloku).
- **[s9q6yb]** Film = załącznik `video/mp4`; niewybrany, usunięty albo innego typu — blok pokazuje zdjęcie. Plik mobile — opcjonalny, na tych samych zasadach; brak — plik desktop. Wyjątek — Karty informacyjne na zdjęciu: warstwy desktop i mobile są osobne, brakująca kreacja pokazuje obraz zastępczy (na telefonie bez pliku mobile — obraz zastępczy, nie film desktop; README bloku).
- **[2x6csc]** Plik mobile obowiązuje poniżej 1024 px (`max-width: 1023px`), w Kartach informacyjnych — poniżej 640 px; plik wybiera przeglądarka (`<source media>` mobile przed źródłem desktop) — film startuje bez czekania na JS; `feuer-film` przeładowuje film przy zmianie szerokości przez próg (np. obrót tabletu).
- **[rwzyce]** `<video autoplay muted loop playsinline>` bez kontrolek i bez przycisku pauzy; bez atrybutu `poster`.
- **[qv34eu]** Film pierwszego ekranu (hero, Top visual kontentowy) — adresy w `src`, pobierany od razu, plakat `loading="eager"`, `fetchpriority="high"` (element LCP); poniżej pierwszego ekranu (Belka informacyjna, Karty informacyjne poza hero; plakat `loading="lazy"`) — adresy w `data-src`, pobieranie startuje raz na film moduł `feuer-film` ok. jednego ekranu przed widokiem (`IntersectionObserver`, `rootMargin` 100%); do tego czasu widać plakat.
- **[wmk54b]** Plakat — `<picture class="film-plakat">` pod filmem, widoczny do startu filmu: obrazek wyróżniający pliku desktop (`full`, atrybuty z bloku) i `<source>` plakatu pliku mobile; plakatu nie ma, gdy brakuje go któremuś użytemu plikowi.
- **[gc2jv2]** Podgląd w kanwie edytora — plik desktop; wyjątek: Karty informacyjne na zdjęciu — obie warstwy (desktop i mobile), przełączane szerokością kanwy (README bloku).

## Zakładki i akordeon

- **[shjsey]** Zakładki i akordeon grup — moduł `js/zakladki.js`, własny kod bez biblioteki: kontener `[data-zakladki]` z parami przycisk `[data-zakladka]` + panel; ten sam markup to na desktopie pasek zakładek, poniżej 1024 px akordeon — układ z CSS, zachowanie ze skryptu (próg `max-width: 1023px` w skrypcie i CSS bloków).
- **[w69jmg]** Stan: `aria-expanded` na przycisku, `hidden` na panelu za przyciskiem w kolejności dokumentu; semantyka akordeonu (`aria-controls`), bez ról `tablist` / `tab` / `tabpanel` (rola `tablist` dopuszcza wyłącznie zakładki) i bez `aria-selected`, także w układzie zakładek; bez nawigacji strzałkami — wyłącznie klik.
- **[7gaapj]** Tryb domyślny, od 1024 px: zawsze dokładnie jedna aktywna grupa, klik w aktywną nic nie zmienia; nowy panel wjeżdża przenikaniem 400 ms, poprzedni chowa się od razu; powrót z mobile bez aktywnej grupy aktywuje pierwszą.
- **[ayw6t7]** Tryb domyślny, poniżej 1024 px (akordeon): klik w zamkniętą grupę otwiera ją i zamyka pozostałe, klik w otwartą zwija ją (wszystkie mogą być zwinięte); rozwijanie i zwijanie animowane 400 ms, jak obrót chevrona.
- **[h87yhn]** Tryb `akordeon` (FAQ): każda pozycja przełączana niezależnie na każdej szerokości, z animacją wysokości. Tryb `zakladki`: zakładki na każdej szerokości — nieużywany przez bloki. Tryb wybiera atrybut kontenera `data-zakladki` (`akordeon`, `zakladki`, bez wartości — domyślny); pozycja — przycisk `data-zakladka` z `aria-expanded` i `aria-controls`, panel na starcie `hidden`.

## Karuzele

- **[d5anc2]** Karuzele kart — Swiper (architektura-kodu.md, [enwfdx]): Karty informacyjne na zdjęciu i Zobacz także — `slidesPerView: 'auto'`, wskaźnik z kresek (klikalny), bez pętli i autoplay, przewijanie poziome kółkiem albo trackpadem (pionowe przewija stronę); Karuzela szkoleń — README bloku.
- **[974r7r]** Karty informacyjne na zdjęciu i Zobacz także chowają wskaźnik, gdy wszystkie slajdy mieszczą się w widoku (także przy jednym slajdzie); Karuzela szkoleń z jedną kartą pokazuje jedną kreskę (styl wskaźnika z motywu przesłania ukrycie paginacji Swipera).
- **[95e2p7]** Kreski wskaźnika (`<span>` paginacji) nie dostają fokusu; Tab wchodzi w niewidoczne slajdy.

## Elementy wspólne

- **[pggtsm]** Podkreślenie etykiety kategorii (`.etykieta-kategorii`, atom A47) ma szerokość dwóch pierwszych słów tekstu (jednego przy jednym słowie): mierzy ją `js/etykieta-kategorii.js` (Range → `--szerokosc-podkreslenia`) po załadowaniu fontów i przy każdej zmianie rozmiaru okna; pomiar zerowy nie nadpisuje wartości.
- **[3r3tf7]** Pole wyboru (atom A53, `js/rozwijane.js`): klik pozycji przenosi jej tekst do pola, oznacza ją (`aria-selected`) i zamyka listę; otwieranie i zamykanie listy — [nawigacja.md](nawigacja.md), [xnzbtx]; przy otwarciu skrypt ogranicza szerokość listy do prawej krawędzi ekranu minus 16 px.

## Kod QR

- **[9ybcp6]** Edytor wpisu typu publicznego (strony, produkty, artykuły; nie sekcje, eksperci, edytor witryny, widgety) ma w górnym pasku, za „Podgląd", przycisk „Kod QR" (sama ikona, etykieta w podpowiedzi); bez osobnego sprawdzenia uprawnień; niewidoczny, dopóki wpis nie ma adresu.
- **[fjpsz4]** Przycisk otwiera okno „Kod QR": podgląd kodu (SVG, przeliczany przy zmianie adresu), pełny adres, „Pobierz PNG" (1000 × 1000 px) i „Pobierz SVG"; wpis nieopublikowany — niezamykalne ostrzeżenie „Treść nieopublikowana — adres może się jeszcze zmienić."
- **[6v98qe]** Adres w kodzie: zawsze `https://www.feuer.pl` + ścieżka i parametry adresu wpisu — także na serwerze dev i w lokalnej instancji dev.
- **[syqfv7]** Plik `kod-qr-<ostatni niepusty segment ścieżki>.png` / `.svg` (strona główna — `kod-qr-strona-glowna`), generowany w przeglądarce i pobierany lokalnie; nic nie trafia do WordPressa (bez biblioteki mediów).
- **[vw6gzz]** Wzór kodu: korekcja błędów H, margines 4 moduły, co najmniej wersja 4 (33 × 33 moduły); na środku czerwony sygnet Feuer (kształt z `ikony/logo.svg`) szeroki na 10 modułów w kole o promieniu 6,5 modułu wolnym od danych — moduł zachodzący na koło pomijany w całości; sygnet i koło mają stałą wielkość w modułach.
- **[8pv3r5]** SVG: 10 px na moduł, białe tło, czarne moduły (`shape-rendering=crispEdges`), czerwony sygnet. PNG: rysowany na canvas, krawędzie modułów zaokrąglone do pełnych pikseli.
- **[uqbrgh]** Skrypt `feuer-kod-qr` — osobny wpis buildu (`src/kod-qr/` → `build/kod-qr/`, `webpack.config.js`) z biblioteką `qrcode-generator` (npm; wersja — architektura-kodu.md, [23yh8r]), ładowany wyłącznie w edytorze (stopka ekranu edycji wpisu; zależności i wersja z `build/kod-qr/index.asset.php`); teksty przez i18n (domena `feuer-komponenty`).

## Rejestr

Typ: T, D, R, S (szablonowy) — „Typy bloków". Gdzie: „treść" = treść wpisu dowolnego typu (whitelisty nie ma — [uprawnienia.md](uprawnienia.md), [tpzesj]). Wstawiacz: kategoria (`category`) albo „ukryty" (`inserter: false`).

- **[2s88n5]** Kategoria wstawiacza bloku — `category` w `block.json` (kolumna „Wstawiacz").
- **[b4jwt5]** Żaden blok firmowy nie ma trybu edycji jako HTML (`supports.html: false`).
- **[ecp7bd]** Bez zapisu jako blok wielokrotnego użytku (`supports.reusable: false`): bloki ramy i szablonowe, bloki zawartości sekcji (`belka-zapowiedzi-dane`, `dane-kontaktu`, `terminy-brak`, `zgoda`), bloki potomne (pozycja, krok, pytanie, karta, kolumna) i Lista artykułów; bloki potomne dodatkowo bez blokady (`supports.lock: false`).
- **[ab85qy]** `block.json` bloku: schemat atrybutów, `parent`, `allowedBlocks` (strefom treści redakcyjnej nadaje je filtr palety), `description`, `example` z kanoniczną treścią (podgląd we wstawiaczu); `example` pusty (`{}`) — `artykul`, `baza-wiedzy`, `belka-zapowiedzi`, `branza`, `kategoria`, `lista-artykulow`, `okruszki`, `sprawdz-takze`; bez `example` — `dane-kontaktu`, `terminy-brak`, `zgoda`.
- **[7ws8qv]** Opis bloku — `README.md` w folderze bloku ([DOC-README-BLOCK], szablon „Blok": zasady-dokumentacji.md, „Szablony dokumentów").

| ID | Blok | Typ | Gdzie | Wstawiacz | README |
|---|---|---|---|---|---|
| **[a9hhrj]** | `feuer/aktualnosci` — Aktualności | D | treść | widgets | [README](blok-aktualnosci.md) |
| **[6f294p]** | `feuer/artykul` — Artykuł | S | szablon wpisu (`single.html`) | ukryty | [README](blok-artykul.md) |
| **[2ns2fh]** | `feuer/baza-wiedzy` — Strona Bazy wiedzy | S | szablon strony z wpisami (`home.html`) | ukryty | [README](blok-baza-wiedzy.md) |
| **[chsz3a]** | `feuer/belka-info` — Belka informacyjna | T | treść | design | [README](blok-belka-info.md) |
| **[avhcva]** | `feuer/belka-zapowiedzi` — Belka zapowiedzi | D | treść; dane z sekcji `belka-zapowiedzi` | design | [README](blok-belka-zapowiedzi.md) |
| **[7c742n]** | `feuer/belka-zapowiedzi-dane` — Belka zapowiedzi — treść | T | sekcja `belka-zapowiedzi`; jeden | ukryty | [README](blok-belka-zapowiedzi-dane.md) |
| **[c39d8n]** | `feuer/branza` — Strona branży | S | szablon strony branży (`taxonomy-branza.html`) | ukryty | [README](blok-branza.md) |
| **[4updw3]** | `feuer/cytat` — Opinia klienta | T | treść; paleta | text | [README](blok-cytat.md) |
| **[zgmse2]** | `feuer/dane-kontaktu` — Dane kontaktu | T | sekcja `dane-kontaktu`; jeden | ukryty | [README](blok-dane-kontaktu.md) |
| **[d9sgfg]** | `feuer/dla-kogo` — Dla kogo | T | treść | design | [README](blok-dla-kogo.md) |
| **[wkksec]** | `feuer/dla-kogo-pozycja` — Pozycja | T | wewnątrz `feuer/dla-kogo` | design | [README](blok-dla-kogo-pozycja.md) |
| **[2uktfq]** | `feuer/dwie-kolumny` — Dwie kolumny | T | treść; paleta | text | [README](blok-dwie-kolumny.md) |
| **[9dwgnv]** | `feuer/dwie-kolumny-kolumna` — Kolumna | T | wewnątrz `feuer/dwie-kolumny` | ukryty | [README](blok-dwie-kolumny-kolumna.md) |
| **[ppjc6b]** | `feuer/faq` — FAQ | T | treść; jeden na stronę | design | [README](blok-faq.md) |
| **[8mwgg5]** | `feuer/faq-pytanie` — Pytanie | T | wewnątrz `feuer/faq` | design | [README](blok-faq-pytanie.md) |
| **[s8zwzh]** | `feuer/kafelki-branz` — Kafelki branż | D | treść | widgets | [README](blok-kafelki-branz.md) |
| **[gdqar2]** | `feuer/kafle-kategorii` — Kafle kategorii | D | treść | widgets | [README](blok-kafle-kategorii.md) |
| **[3vnd43]** | `feuer/kafle-produktowe` — Kafle produktowe | D + T | treść; sekcja branży (zablokowany) | widgets | [README](blok-kafle-produktowe.md) |
| **[6h4tsa]** | `feuer/kalendarium` — Kalendarium | D | treść | widgets | [README](blok-kalendarium.md) |
| **[fn22b6]** | `feuer/karta-opisu-produktu` — Karta opisu produktu (Program) | T | treść | design | [README](blok-karta-opisu-produktu.md) |
| **[uz8cer]** | `feuer/karta-opisu-produktu-pozycja` — Pozycja (etap) | T | wewnątrz `feuer/karta-opisu-produktu` | design | [README](blok-karta-opisu-produktu-pozycja.md) |
| **[eukcyh]** | `feuer/karty-informacyjne` — Karty informacyjne na zdjęciu (także hero strony głównej) | T | treść | design | [README](blok-karty-informacyjne.md) |
| **[xqgrsk]** | `feuer/karty-informacyjne-karta` — Karta informacyjna | T | wewnątrz `feuer/karty-informacyjne` | design | [README](blok-karty-informacyjne-karta.md) |
| **[42tv69]** | `feuer/karuzela-szkolen` — Karuzela szkoleń na zdjęciu | D | treść | widgets | [README](blok-karuzela-szkolen.md) |
| **[e52udu]** | `feuer/kategoria` — Strona kategorii | S | szablon strony kategorii (`taxonomy-oferta.html`) | ukryty | [README](blok-kategoria.md) |
| **[z762q8]** | `feuer/kluczowe-informacje` — Kluczowe informacje | T (wstęp) / D (tabela z danych) | treść | design | [README](blok-kluczowe-informacje.md) |
| **[nrrrga]** | `feuer/lista-artykulow` — Lista artykułów | D | treść; sekcja `baza-wiedzy` | widgets | [README](blok-lista-artykulow.md) |
| **[55srf6]** | `feuer/naglowek` — Header serwisu (z menu głównym) | R + D | sekcja `naglowek-serwisu` | ukryty | [README](blok-naglowek.md) |
| **[864r5q]** | `feuer/okruszki` — Okruszki / link wstecz | S | szablony stron, produktu, Bazy wiedzy, branży, `index.html` | ukryty | [README](blok-okruszki.md) |
| **[mqctt2]** | `feuer/proces-wspolpracy` — Proces współpracy | T | treść | design | [README](blok-proces-wspolpracy.md) |
| **[qan54x]** | `feuer/proces-wspolpracy-krok` — Krok | T | wewnątrz `feuer/proces-wspolpracy` | design | [README](blok-proces-wspolpracy-krok.md) |
| **[2xaue9]** | `feuer/sekcja` — Sekcja (po slugu) | S | części szablonu `naglowek`, `stopka` | ukryty | [README](blok-sekcja.md) |
| **[kec496]** | `feuer/sekcja-kontaktowa` — Sekcja kontaktowa | T | treść | design | [README](blok-sekcja-kontaktowa.md) |
| **[2n93dy]** | `feuer/sprawdz-takze` — Sprawdź także | T | treść; paleta | text | [README](blok-sprawdz-takze.md) |
| **[qbgws9]** | `feuer/stopka` — Stopka serwisu | R + D | sekcja `stopka-serwisu` | ukryty | [README](blok-stopka.md) |
| **[5qr9yg]** | `feuer/szare-tlo` — Szare tło | T | treść, między sekcjami; poza strefami treści | text | [README](blok-szare-tlo.md) |
| **[f26wke]** | `feuer/tekst-zdjecie` — Sekcja tekst+zdjęcie | T | treść | design | [README](blok-tekst-zdjecie.md) |
| **[nh7824]** | `feuer/terminy` — Terminy | D | treść | widgets | [README](blok-terminy.md) |
| **[k38j8v]** | `feuer/terminy-brak` — Terminy — stan pusty | T | sekcja `terminy-brak`; jeden | ukryty | [README](blok-terminy-brak.md) |
| **[6k3kpy]** | `feuer/top-kontentowy` — Top visual kontentowy | T | wzorzec „Strona kontentowa", zestaw startowy sekcji branży, sekcja `baza-wiedzy`; jeden na stronę | ukryty | [README](blok-top-kontentowy.md) |
| **[vseg6m]** | `feuer/top-listingu` — Top visual listingu | T / D (sekcja kategorii) | treść; sekcja kategorii; jeden na stronę | design | [README](blok-top-listingu.md) |
| **[kd3dww]** | `feuer/top-produktowy` — Top visual produktowy | D + T | wzorce produktu (pierwsza pozycja); jeden na stronę | ukryty | [README](blok-top-produktowy.md) |
| **[t6shq5]** | `feuer/zgoda` — Zgoda RODO | T | sekcja `zgoda-rodo`; jeden | ukryty | [README](blok-zgoda.md) |
| **[7hvzed]** | `feuer/zobacz-takze` — Zobacz także | D | treść | widgets | [README](blok-zobacz-takze.md) |
