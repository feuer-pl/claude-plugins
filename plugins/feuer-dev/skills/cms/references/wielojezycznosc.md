# Wielojęzyczność

Wersje językowe serwisu: mechanizm (Polylang), języki i adresy, zakres tłumaczeń, abstrakcja tłumaczeń w kodzie, przełącznik języka, i18n. Tłumaczenia obiektów: [produkt.md](produkt.md), [sekcje.md](sekcje.md), [artykuly.md](artykuly.md), [taksonomie.md](taksonomie.md), [media.md](media.md); `/en/` do startu wersji EN: przekierowania.md.

## Stan

- **[6s8z8b]** Serwis działa po polsku: wszystkie strony, artykuły i produkty mają język polski; angielski jest skonfigurowany, bez treści i tłumaczeń (jedyny obiekt angielski — term rubryki „Bez kategorii"). Wersja EN nie wystartowała — `/en/` przekierowuje na `/` (przekierowania.md, [b9dk35]).

## Mechanizm

- **[n5cjs8]** Polylang w wersji Free (rejestr wordpress.org): języki jako taksonomia WordPressa, tłumaczenie = osobny wpis powiązany z oryginałem (hreflang — [seo.md](seo.md), [bz5nmq]).
- **[t7ddvu]** Polylang Pro — dopiero przy potrzebie (tłumaczone slugi baz adresów, duplikacja treści przy tworzeniu tłumaczenia); przejście Free → Pro bez migracji.
- **[cqfff6]** API `pll_*` w PHP (dostępne we Free, m.in. `pll_set_post_language()`, `pll_save_post_translations()`) pozwala tworzyć tłumaczenia programowo; przez REST Polylang Free nie ustawia języka wpisu ani powiązań tłumaczeń.
- **[qpbavn]** Ograniczenia Free nie dotykają architektury: typy FSE (`wp_template`, `wp_template_part`, `wp_navigation`) są poza filtrowaniem językowym — szablony i części szablonu wspólne dla języków; części szablonu wstawiają sekcję po slugu ([sekcje.md](sekcje.md), [8vsg6f]), menu jest własnym blokiem ([nawigacja.md](nawigacja.md), [73yqkj]).

## Języki i adresy

- **[2jpw8b]** Języki: Polski (`pl`, `pl_PL`, flaga `pl`, kolejność 0) — domyślny; English (`en`, `en_US`, flaga `us`, kolejność 1). Konfiguracja identyczna na lokalnej instancji dev, serwerze dev i produkcji (te same term ID języków).
- **[skc5n2]** Adresy katalogowe: PL bez prefiksu, pozostałe języki z prefiksem (`/en/…`), bez `/language/` w adresie (`force_lang` = 1, `hide_default`, `rewrite`) — opcje domyślne Polylang, niezmieniane.
- **[9khvss]** Bazy adresów zostają polskie także w innych językach (Free): `/en/szkolenia/…`; artykuł EN — `/en/baza-wiedzy/<slug>/` (prefiks struktury odnośników wpisów nietłumaczony; czy Pro go tłumaczy — niepotwierdzone).
- **[864eka]** Bez wykrywania języka przeglądarki (`browser` = false); adres strony głównej w innym języku — z nazwą strony, nie samym kodem języka (`redirect_lang` = false).
- **[6x8ymu]** Adres z prefiksem `/en/` dla istniejącej treści polskiej (np. `/en/oferta/`, `/en/szkolenia/<slug>/`) — 301 Polylanga na adres polski (`X-Redirect-By: Polylang`); dla termów `oferta` i `branza` (`/en/oferta/<slug>/`, `/en/branza/<slug>/`) i treści nieistniejącej — 404; sam `/en/` — reguła Redirection.
- **[3cfpss]** Bez menu przypisanych do języków i bez domen języków (`nav_menus`, `domains` puste).
- **[qskeq2]** Język WordPressa — polski: infrastruktura.md, [88qm7r].

## Zakres tłumaczeń

- **[n7fr7r]** Tłumaczone typy wpisów: `post`, `page`, `wp_block` (domyślne Polylang) i `produkt` (dopisany filtrem `pll_get_post_types`, niezależnie od ustawień Polylang); nietłumaczone: `sekcja` ([sekcje.md](sekcje.md), [8bcbuy]), `ekspert`, media ([media.md](media.md), [mza4r8]).
- **[7n3mcs]** Tłumaczone taksonomie: `category`, `post_tag`; nietłumaczone: `oferta`, `branza`, `grupa`, `oznaczenie` — tłumaczenie produktu nie dostaje termów `oferta` i `branza`.
- **[jrtygf]** Ustawienie synchronizacji Polylang (`sync`) jest puste — żaden element wbudowany (taksonomie, pola własne, obrazek wyróżniający, szablon, data, kolejność) nie jest synchronizowany ustawieniem; synchronizowane są wyłącznie meta produktu i taksonomia `oznaczenie`, dopisane filtrami wtyczki ([produkt.md](produkt.md), [wv5rjc]) — w obie strony (PL ↔ EN), także przy zapisie przez REST.
- **[4htqwa]** Listingi automatyczne (zapytania o produkty i artykuły) pokazują wyłącznie wpisy w języku strony — filtr zapytań Polylang. Menu (drzewo termów `oferta` — taksonomia nietłumaczona), linki statyczne headera i wybór ręczny pozycji nie pomijają wpisów bez tłumaczenia — abstrakcja tłumaczeń jest przechodnia.
- **[knzm2q]** „Tłumaczenia ciągów" Polylang — zapisane wyłącznie dla nazwy witryny (infrastruktura.md, [eaqenh]; w obu językach tak samo); kod serwisu nie rejestruje własnych ciągów (`pll_register_string`, `pll__`).

## Abstrakcja tłumaczeń

- **[kyvf24]** Kod bloków rozwiązuje wpisy i termy na wersję w bieżącym języku wyłącznie przez abstrakcję `includes/tlumaczenia.php` — bez wywołań Polylang wprost: `feuer_wpis_w_biezacym_jezyku()` (bez tłumaczenia — oryginał), `feuer_tlumaczenie_wpisu()` (bez fallbacku: 0 = brak; w podglądzie edytora bieżący język = język edytowanego wpisu), `feuer_term_w_biezacym_jezyku()` (bez tłumaczenia — oryginał). Użycie: sekcja po slugu, produkt i kategoria wskazane atrybutem, linki z ID ([bloki.md](bloki.md), [a4xc8h]), wybór ręczny pozycji ([bloki.md](bloki.md), [86nqk3]).
- **[bacp9q]** Abstrakcja jest przechodnia: wszystkie trzy funkcje zwracają przekazane ID (oryginał), więc każdy wpis „ma tłumaczenie" — pozycje bez tłumaczenia nie odpadają. Rozwiązywanie tłumaczeń przez Polylang — stan planowany (wdrożenie wersji językowych).
- **[b8tb5u]** Link do wpisu wskazanego ID, który nie ma tłumaczenia w bieżącym języku (np. powiązany artykuł Top visualu produktowego) — adres w języku strony, dalej fallback stron — stan planowany; dziś — adres oryginału.
- **[uu66fp]** Kod bieżącego języka (`feuer_biezacy_jezyk()`) — dwa pierwsze znaki `determine_locale()` (np. `pl`); służy do kluczy cache zależnych od języka (transient drzewa oferty — wariant na język).
- **[52dzrm]** Edytor (REST bez parametru języka) pokazuje produkty wszystkich języków, front — tylko języka strony; produkt bez języka dawałby różną liczbę kart (dziś każdy produkt ma język).

## Przełącznik języka

- **[7d2mfu]** Przełącznik języka jest częścią bloku headera `feuer/naglowek` ([nawigacja.md](nawigacja.md)) i jest wyłączony: header go nie renderuje (desktop i menu mobile); przycisk headera (E-learning) stoi na desktopie przy prawej krawędzi. Kod przełącznika (style, `feuer_jezyki()`, flagi) zostaje — włączenie = przywrócenie bieżącego języka w `feuer/naglowek`.
- **[2eb6ac]** Lista języków przełącznika jest stała, w kodzie, niezależna od języków Polylang (`feuer_jezyki()`): Polski (`pl`, PL, `flaga-pl.svg`), English (`en`, EN, `flaga-us.svg`); pozycja: kod, skrót, nazwa, flaga (plik z `ikony/` wtyczki), adres, bieżący. Adres każdej pozycji — strona główna; bieżąca — pozycja o kodzie bieżącego języka (język spoza listy — żadna). Nowy język wymaga zmiany listy w kodzie.
- **[nm3m42]** Przełącznik: przycisk z flagą, kodem języka i strzałką; po otwarciu (`aria-expanded`) lista języków z flagami (bieżący wyróżniony); pozycje to zwykłe linki — przełączanie języka = nawigacja.

## Zasady redakcyjne

- **[v6pmq5]** Polski jest językiem głównym: tłumaczenia powstają z polskiego oryginału, nigdy odwrotnie; publikacja i edycja PL nie czeka na tłumaczenia (PL-first).
- **[feambn]** Potok tłumaczeń AI — stan planowany: akcja w panelu → polski oryginał → tłumacz → krytyk w języku docelowym → korekta → szkic tłumaczenia do akceptacji w edytorze; realizacja API `pll_*` w PHP; nieaktualność tłumaczenia wykrywa hash treści PL zapisany w meta tłumaczenia.

## I18n

- **[v25q78]** Teksty interfejsu w kodzie (PHP, JS) — przez funkcje i18n z domeną `feuer-komponenty`, bez zaszytych stringów; logika bloków bez założeń „tylko PL".
- **[p5d9rn]** Plików tłumaczeń (`.po`, `.mo`) nie ma: katalog `languages/` wtyczki (nagłówek `Domain Path: /languages`, tłumaczenia skryptów edytora) nie istnieje — teksty interfejsu, także znaczniki `<wprowadź dane>` i napisy paneli edytora, wyświetlają się po polsku w każdym języku.
