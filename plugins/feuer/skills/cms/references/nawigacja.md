# Nawigacja

Header i menu główne (drzewo oferty, cache), elementy rozwijane, okruszki i link wstecz, flaga „Strona lądowania". Pola bloków ramy: [README bloku `naglowek`](blok-naglowek.md), [README bloku `stopka`](blok-stopka.md), [README bloku `okruszki`](blok-okruszki.md); sekcje ramy: [sekcje.md](sekcje.md); szablony: [strony.md](strony.md); taksonomie: [taksonomie.md](taksonomie.md).

## Header i menu

- **[73yqkj]** Menu serwisu to blok `feuer/naglowek` w sekcji `naglowek-serwisu` ([sekcje.md](sekcje.md), [2ysenk]); menu jest kodem — drzewo oferty budowane w bloku z taksonomii. Natywne menu WordPressa nie jest używane (w bazie 0 menu, `nav_menu_locations` puste, domyślny wpis `wp_navigation` nieużywany), `core/navigation` też nie.
- **[y2k9ag]** Menu = jeden obiekt dla użytkownika: drzewo oferty (kategorie najwyższego poziomu w wierszu menu, podkategorie w panelach) i pozycje statyczne — linki pomocnicze (np. Baza wiedzy, O firmie, Kontakt: górny rząd headera i dół menu mobile) oraz przycisk headera (E-learning); edycja — pola bloku w sekcji `naglowek-serwisu` ([README bloku `naglowek`](blok-naglowek.md)).
- **[yabv7x]** Utworzenie, zmiana albo usunięcie termu `oferta` w CMS widać w menu i stopce bez zmian w kodzie. Kategoria znika z menu dopiero po usunięciu termu (bez flagi wyłączenia z menu); jej strona jest zawsze generowana.
- **[2b9qxk]** Drzewo oferty (`feuer_drzewo_oferty()`) — źródło menu, stopki, drzew kategorii i sekcji kategorii `/llms.txt` ([seo.md](seo.md), [ey63x9]): wszystkie termy `oferta`, także puste, na każdym poziomie ([taksonomie.md](taksonomie.md), [xktvsv], [66s4x2]); węzeł: ID, slug, nazwa termu (bez nazw skróconych), adres strony termu, podkategorie.
- **[3sxrwm]** Cache drzewa: jeden transient `feuer_drzewo_oferty` (24 h od ostatniego zapisu) z tablicą wariantów per język ([wielojezycznosc.md](wielojezycznosc.md), [uu66fp]); wariant powstaje przy pierwszym użyciu w danym języku (zapis odnawia czas życia całego transientu). Utworzenie, edycja i usunięcie termu `oferta` kasują cały transient — wszystkie warianty naraz.
- **[ppue8x]** Wiersz menu desktop — kategorie najwyższego poziomu: kategoria z podkategoriami to przycisk z caretem (`data-rozwijane`, `aria-expanded`) otwierający panel pod wierszem menu, kategoria bez podkategorii — zwykły link bez caretu i panelu. Menu pokazuje 2 poziomy drzewa; głębszych nie.
- **[gnbehk]** Panel (mega-panel na szerokość treści; ciemny przy ciemnym headerze, jasny przy jasnym): tytuł — nazwa kategorii; podkategorie ze strzałką i linią w kolumnach — 2, gdy panel ma blok „Branże", inaczej 3; w kolumnie ceil(n/k) pozycji z góry na dół (7 → 4/3), kolumny to osobne listy o niezależnej wysokości; link akcji „Sprawdź całą ofertę" (tekst zaszyty, i18n) — adres: pole bloku ([README bloku `naglowek`](blok-naglowek.md), [t3etq2]).
- **[7bcyz9]** Blok „Branże" po prawej w każdym panelu kategorii (włączany polem bloku — [README bloku `naglowek`](blok-naglowek.md), [qtgmdh]): nagłówek „Branże" (tekst zaszyty, i18n, bez linku); wszystkie branże z taksonomii `branza` (także puste) w kolejności listy branż ([taksonomie.md](taksonomie.md), [4c6qy5]) — linki do stron branż: okrągłe zdjęcie z meta termu (miniatura, alt pusty, ładowanie leniwe; obowiązkowe — brak = obraz zastępczy) i nazwa, bez strzałek. Ten sam blok w panelu jasnym i ciemnym, to samo źródło co Kafelki branż (`feuer_branze()`); bez żadnej branży — bez bloku; menu mobile — bez bloku.
- **[wj34k9]** Menu rozwija się klikiem (nie najazdem), otwarta jest jedna pozycja; klik wewnątrz panelu nie zamyka, Escape i klik poza — zamykają. Pozycja rozwinięta: tekst w kolorze marki (na ciemnym — biały), caret w górę, pasek akcentu pod pozycją. Pozycje menu nie oznaczają bieżącej sekcji (bez `aria-current` i klasy).
- **[hqr9c9]** Hover pozycji wiersza menu, podpozycji panelu, pozycji bloku „Branże" i linków pomocniczych headera (także w menu mobile) — tekst w kolorze marki; kategorie i podpozycje menu mobile bez hovera. Ramka fokusu — tylko przy klawiaturze (`:focus-visible`).
- **[z85qhw]** Mobile: header — belka z logo i hamburgerem (`aria-label` „Otwórz menu", po otwarciu „Zamknij menu" — teksty z HTML, przez i18n). Hamburger otwiera warstwę menu na pełny ekran (header `position: fixed`; przy ciemnym headerze cała warstwa ciemna); ikona — trzy kreski, po otwarciu X, przy zamykaniu wraca od razu.
- **[gf4ktz]** Menu mobile ma dwa poziomy: główny — kategorie najwyższego poziomu ze strzałką (z podkategoriami — przycisk, cały wiersz, przechodzący na poziom kategorii; bez podkategorii — link), na dole linki pomocnicze i przycisk headera na całą szerokość; poziom kategorii — przycisk „← nazwa kategorii" (powrót) i podkategorie ze strzałką, bez linków pomocniczych, przycisku i linku „Sprawdź całą ofertę". Każde otwarcie zaczyna od poziomu głównego; przycisk `[data-poziom]` pokazuje wyłącznie warstwę o tej nazwie.
- **[5bu7br]** Menu mobile zamyka wyłącznie hamburger — bez Escape i kliku poza.
- **[ands5z]** CSS serwisu nie definiuje animacji menu — zmiany stanu są natychmiastowe. Skrypt czeka z zamknięciem menu (`.menu-zamyka`) i zmianą poziomu (`.poziom-wyjazd`) na animacje wyjścia (`getAnimations()`), gdy CSS je zdefiniuje.

## Elementy rozwijane

- **[xnzbtx]** Moduł `rozwijane.js`: klik w `[data-rozwijane]` przełącza `aria-expanded` (przycisk wyłączony — nie), otwarcie jednego zamyka pozostałe (menu główne, przełącznik języka, pozycje okruszków, pola wyboru); Escape i klik poza zamykają wszystkie otwarte (klik w otwartym `.menu-panel` nie jest „poza"). Wygląd stanu otwartego — CSS po `aria-expanded`.
- **[p6ug2v]** Wyjątek `data-rozwijane="akordeon"` (grupy oferty w stopce mobilnej, drzewo kategorii): elementy otwierają się niezależnie i nie zamykają od Escape, kliku poza ani otwarcia innego elementu.

## Okruszki i link wstecz

- **[jg6qr3]** Ścieżkę okruszków i link „Wstecz" rysuje jedna funkcja `feuer_sciezka_html()`: okruszki widoczne od 1024 px szerokości kontenera ścieżki, poniżej — link „← Wstecz" (container query `.sciezka`). Pusta ścieżka — bez okruszków, linku i danych `BreadcrumbList` ([seo.md](seo.md), [kcpv6v]).
- **[a2shcq]** Blok `feuer/okruszki` stawia rząd `.pas-okruszki` pod headerem (szablony: [bloki.md](bloki.md), [864r5q]), tylko przy niepustej ścieżce; link „Wstecz" niosą sekcje otwierające (top visual kontentowy, listingu, produktowy, otwarcie artykułu).
- **[xmubhb]** Top visual kontentowy i produktowy: na desktopie okruszki w rzędzie ramy nad blokiem (blok ukrywa własną ścieżkę od 1024 px), poniżej 1024 px na zdjęciu link „Wstecz". Top visual listingu: okruszki na zdjęciu także na desktopie — strona z tym blokiem nie ma rzędu okruszków ramy (`feuer/okruszki` nic nie wypisuje; szablon kategorii nie ma bloku okruszków).
- **[gj2vwz]** Okruszki desktop: `nav` z etykietą „Okruszki", lista uporządkowana; na początku ikona domu — link do strony głównej („Strona główna"). Pozycja z co najmniej dwoma elementami rodzeństwa — przycisk z nazwą i strzałką (`aria-expanded="false"`) rozwijający listę linków do rodzeństwa; pozycja z mniejszym rodzeństwem — zwykły link; ostatnia (bieżąca) — tekst bez linku z `aria-current="page"` (z listą — `aria-current="page"` na jej elemencie). Napisy przez i18n.
- **[e88rgp]** Lista rodzeństwa: bieżący element wyróżniony (`aria-current` — „page" przy ostatniej pozycji ścieżki, inaczej „true"; kolor marki w liście kategorii, półgruby przy bieżącej stronie); pierwszy element listy ma przycisk „Zwiń listę" ze strzałką w górę (bez własnej obsługi — zamyka reguła kliku poza). Na desktopie z myszką (`hover: hover`) lista otwiera się najazdem i znika po zjechaniu (także stan ustawiony klikiem); klik i Enter przełączają listę (klawiatura, dotyk); lista nachodzi na pozycję.

  | ID | Strona | Ścieżka (po ikonie domu) | Link „Wstecz" |
  |---|---|---|---|
  | **[y7hzw8]** | Strona główna | pusta — bez okruszków | — |
  | **[w3zp6m]** | Kategoria oferty | „Oferta" › przodkowie termu (od najwyższego) › term | kategoria nadrzędna; z kategorii najwyższego poziomu — „Oferta" |
  | **[a5kcc7]** | Produkt | „Oferta" › kategorie (term produktu i jego przodkowie) › produkt; produkt bez termu — sam tytuł | kategoria produktu; produkt bez termu — strona główna |
  | **[dd2qsh]** | Artykuł z produktem | ścieżka produktu („Oferta", kategorie z listami) › produkt zwykłym linkiem bez listy › tytuł artykułu; produkt bez kategorii — produkt › tytuł | strona produktu |
  | **[gy9kmk]** | Artykuł bez produktu | strona z wpisami (zwykły link, bez listy) › tytuł; bez strony z wpisami — sam tytuł | strona z wpisami |
  | **[dj2bd8]** | Zwykła strona, strona z wpisami | strony nadrzędne (od najwyższej) › strona; każda pozycja z listą rodzeństwa | strona nadrzędna; bez niej — strona główna |
  | **[gv9nfq]** | Strona lądowania | sam tytuł, bez stron nadrzędnych i listy | strona główna |
  | **[qk3a5s]** | Strona branży | branża z listą wszystkich branż (kolejność — [taksonomie.md](taksonomie.md), [4c6qy5]); strony „Branże" nie ma | strona główna |
  | **[nb4dev]** | Pozostałe widoki (archiwa rubryk i tagów, wyniki wyszukiwania, 404) | pusta | — |

- **[ercacg]** Pozycja „Oferta" — link do opublikowanej strony o ścieżce `oferta` (nazwa = tytuł strony, rozwiązana na bieżący język przez abstrakcję tłumaczeń), bez listy; bez opublikowanej strony — bez pozycji, a link wstecz kategorii najwyższego poziomu prowadzi na stronę główną.
- **[xs7vwz]** Lista rodzeństwa kategorii: termy `oferta` o tym samym rodzicu, także puste ([taksonomie.md](taksonomie.md), [xktvsv]).
- **[x5ndq6]** Lista przy pozycji produktu: opublikowane produkty przypięte bezpośrednio do termu produktu (bez podkategorii), bez limitu, alfabetycznie po tytule wpisu (kolejność wyznacza kolacja bazy), w języku strony (filtr zapytań Polylang); nazwa pozycji — tytuł wpisu, nie nazwa skrócona. Produkt z flagą „Nie pokazuj w listingu kategorii" stoi na liście przy własnej pozycji, z list innych produktów jest pominięty.
- **[n3bxrb]** Lista rodzeństwa stron: opublikowane strony o tym samym rodzicu, bez strony głównej, wg `menu_order`, przy równej — wg tytułu (strona najwyższego poziomu — strony najwyższego poziomu).
- **[beqnp4]** Link „Wstecz" prowadzi do przedostatniej pozycji ścieżki (elementu nadrzędnego bieżącej strony); ścieżka z jedną pozycją — do strony głównej.

## Strona lądowania

- **[wb4bm9]** Flaga „Strona lądowania" stron (`page`): meta `_feuer_strona_ladowania` (logiczna, domyślnie fałsz, w REST; zapis — `edit_pages`), pole wyboru w panelu „Strona lądowania" panelu dokumentu edytora strony, z tekstem pomocy „Strona nie pojawia się na listach rozwijanych okruszków innych stron; jej okruszki: strona główna › tytuł."; zapis razem ze stroną. Panel — plik `includes/strona-ladowania.js` bez buildu.
- **[xx6njh]** Strona z flagą jest pomijana na listach rodzeństwa okruszków innych stron — poza listą przy własnej pozycji w ścieżce jej strony podrzędnej; jej własne okruszki: [gv9nfq].
- **[xnf5aq]** Flaga nie jest synchronizowana między tłumaczeniami strony — na tłumaczeniu ustawia się ją osobno.
