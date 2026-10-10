# Strony

Typy stron i szablony motywu, rama strony, struktura adresów, strony błędów, ikona witryny, typy stron pominięte. Strony zbiorcze oferty i branż: [strony-zbiorcze.md](strony-zbiorcze.md); Baza wiedzy i artykuły: [baza-wiedzy.md](baza-wiedzy.md); header, menu, stopka i okruszki: [nawigacja.md](nawigacja.md); wzorce stron: [wzorce-stron.md](wzorce-stron.md); bloki: [bloki.md](bloki.md).

## Typy stron i szablony

Motyw blokowy `feuer-skorka`: szablony stron złożone z bloków (`templates/`), części szablonu `naglowek` i `stopka` (`parts/`).

| ID | Typ strony | Obiekt | Szablon i rama |
|---|---|---|---|
| **[4tb54z]** | Strona główna | strona statyczna: `show_on_front` = `page`, `page_on_front` = strona `strona-glowna` (ID 5) | `front-page`: header (wariant wg strony — [README bloku `naglowek`](blok-naglowek.md), [w3twdk]), treść strony w `<main>`, stopka, bez okruszków |
| **[a2cvnn]** | Strona | `page` — strony kontentowe („O firmie"), strony filarów, „Oferta", strony lądowania, strony prawne, „Kontakt" | `page`: header, okruszki, treść w `<main>`, stopka; szablon nie wyświetla tytułu — H1 daje blok otwierający (hero, top visual) |
| **[96jd2w]** | Produkt | `produkt` (szkolenie, usługa) | `single-produkt`: rama jak `page` (header, okruszki, treść wpisu w `<main>`, stopka), bez karty artykułu; sekcje stoją wprost w `<main>` |
| **[rstxa4]** | Artykuł | `post` | `single`: blok `feuer/artykul` ([baza-wiedzy.md](baza-wiedzy.md)) |
| **[pccky5]** | Baza wiedzy | strona wpisów (`page_for_posts`) | `home` ([baza-wiedzy.md](baza-wiedzy.md)) |
| **[un7fs7]** | Kategoria oferty, branża | termy `oferta` (`/oferta/<slug>/` — [taksonomie.md](taksonomie.md), [u9pkpc]), `branza` (`/branza/<slug>/` — [wkeeu2]) | `taxonomy-oferta`, `taxonomy-branza` ([strony-zbiorcze.md](strony-zbiorcze.md)) |
| **[tgegdf]** | Strona 404 | — | `404`: header, wzorzec `strona-404`, stopka; bez okruszków |
| **[dr694q]** | Widoki bez własnego szablonu | archiwa rubryk i tagów, wyniki `/?s=` (archiwa autorów, także `?author=N` — 404: [uprawnienia.md](uprawnienia.md), [2528j4]) | `index` (zapasowy): header, okruszki, lista tytułów wpisów jako linków z zapytania dziedziczonego (bez dat, zajawek i stronicowania) w `<main>`, stopka |
| **[4emmgc]** | Strona błędu serwera (5xx) | statyczny plik `blad-serwera.html` | bez WordPressa: samo logo, bez menu i stopki (sekcja „Strona błędu serwera") |

- **[bj92ag]** Strony systemowe (kategoria oferty, branża, Baza wiedzy) = redagowalna sekcja (`kategoria-<slug>`, `branza-<slug>`, `baza-wiedzy` — [sekcje.md](sekcje.md)) + listing bloku firmowego (`feuer/kategoria`, `feuer/branza` z Kaflami produktowymi, `feuer/lista-artykulow`) na zapytaniach w PHP; `core/query` występuje wyłącznie w szablonie zapasowym `index`.
- **[6mg2dq]** Strony lądowania — zwykłe strony (`page`) najwyższego poziomu składane z bloków, z flagą „Strona lądowania" ([nawigacja.md](nawigacja.md)); np. `/orzeczeniabhp/`.
- **[hs3kpp]** Strony prawne: „Polityka bezpieczeństwa" (`/polityka-bezpieczenstwa/`) i „Dane osobowe" (`/dane-osobowe/`) — zwykłe strony z blokami palety treści bezpośrednio w treści, bez top visualu (strona bez H1); linki w pasku prawnym stopki. Strona prywatności WordPressa nie jest wskazana (`wp_page_for_privacy_policy` = 0).
- **[n9j6u5]** Kod zależy od stron rozpoznawanych po slugu (strony najwyższego poziomu): `kontakt` i `o-firmie` (formularz-kontaktu.md), `oferta` ([nawigacja.md](nawigacja.md)); strona główna i strona wpisów — z ustawień Czytania. Strony mają język polski i szablon domyślny (bez ręcznie wybranego).

## Rama strony

- **[j8h7tf]** Części szablonu: `naglowek` (w `theme.json` „Header", obszar `header`) i `stopka` („Stopka", obszar `footer`) wstawiają po slugu sekcje `naglowek-serwisu` i `stopka-serwisu` blokiem `feuer/sekcja` ([sekcje.md](sekcje.md), [8vsg6f]); w szablonach są owinięte w `div`, a elementy `<header>` i `<footer>` wypisują bloki `feuer/naglowek` i `feuer/stopka` ([nawigacja.md](nawigacja.md)).
- **[ku2r4y]** Odstępy między częściami szablonu i między sekcjami w treści stron i produktów — css.md, [s2x592].
- **[uzqjqk]** Bloki szablonowe `feuer/kategoria`, `feuer/branza` i `feuer/baza-wiedzy` nadają `<main>` klasę treści strony (`wp-block-post-content`) — bloki sekcji i Sekcja kontaktowa działają jak w treści strony.
- **[4kcmk7]** Każda strona ma H2 w stopce („Oferta") i w layerze kontaktu („Zostaw nam kontakt", ukryte „Dziękujemy!").

## Adresy

- **[gsgh6b]** Struktura odnośników `/baza-wiedzy/%postname%/`: artykuły — `/baza-wiedzy/<slug>/`; strony, produkty, kategorie oferty i branże — bez tego prefiksu (`with_front` = false).
- **[9trr8q]** Produkt: szkolenie i produkt bez rodzaju — `/szkolenia/<slug>/` (baza typu), usługa — `/uslugi/<slug>/`. Oba adresy rozpoznają każdy produkt; wejście pod adresem drugiego rodzaju — 301 na właściwy (przekierowania.md, [7u6y52]).
- **[qu5h7s]** Reguła `/uslugi/<slug>/` jest w grupie reguł typu (filtr `produkt_rewrite_rules`, priorytet przed Polylang) i obejmuje wyłącznie sam adres produktu: odmiany pod `/uslugi/` (`/embed/`, `/2/`, kanał) dają 404. Dzięki grupie reguł typu Polylang dokłada prefiks języka (`/en/uslugi/<slug>/`) — reguła z `add_rewrite_rule` by go nie dostała.
- **[x79aj3]** `category_base` i `tag_base` puste: archiwa rubryk i tagów leżą pod prefiksem struktury odnośników — `/baza-wiedzy/category/<slug>/`, `/baza-wiedzy/tag/<slug>/` (formaty wpisów — `/baza-wiedzy/type/<slug>/`).
- **[wshqpp]** Typy niepubliczne `sekcja` i `ekspert` mają reguły adresów z prefiksem (`/baza-wiedzy/sekcja/<slug>/`, `/baza-wiedzy/ekspert/<slug>/`), ale wejście pod nie przekierowuje 301 na stronę główną.
- **[4fy8yp]** Archiwa WordPressa stronicują po 10 wpisów (`posts_per_page`); listy serwisu mają własne limity w zapytaniach. Kanał RSS — [artykuly.md](artykuly.md), [srd8za].

## Strona 404

- **[thqah5]** Treść strony 404 — wzorzec motywu `strona-404` (ukryty we wstawiaczu, wyłącznie dla szablonu 404): `<main class="strona-bledu">` z H1 „Strona nie znaleziona" (i18n `feuer-skorka`) i Sekcja kontaktowa bez atrybutów (teksty domyślne, dane kontaktu z sekcji `dane-kontaktu`); bez sekcji redagowalnej.

## Strona błędu serwera

- **[f9rbu8]** Jedna statyczna strona `blad-serwera.html` (motyw, `lang="pl"`), działająca bez WordPressa, dla wszystkich języków: błąd krytyczny PHP i brak bazy (500), tryb konserwacji przy aktualizacjach (503), 502 i 504 (nginx.md, [e8zenp]).
- **[djnje3]** Drop-iny motywu (`dropiny/`, instalowane w `wp-content/`) wypisują `blad-serwera.html` z katalogu motywu `feuer-skorka` (ścieżka wpisana w drop-iny): `php-error.php` — błąd krytyczny PHP (status 500 i `Content-Type: text/html; charset=utf-8`, gdy nagłówki nie wyszły; treść zawsze), `db-error.php` — brak bazy (500), `maintenance.php` — tryb konserwacji (503, `Retry-After: 600`).
- **[rz29zy]** Treść: logo (plik wtyczki `ikony/logo.svg`, alt „Feuer — strona główna") z linkiem do `/`; H1 „Przepraszamy, wystąpił błąd", „Wkrótce wszystko naprawimy." i pod spodem to samo po angielsku (`lang="en"`); karta kontaktu jak w Sekcji kontaktowej (nagłówek „Porozmawiajmy o bezpiecznym starcie", znak Feuer jako awatar, dane kontaktu), bez przycisku — layer kontaktu wymaga WordPressa. Tytuł dokumentu „Przepraszamy, wystąpił błąd – Feuer".
- **[2mewty]** Style: ten sam font Google Fonts, pliki CSS motywu (tokeny, siatka, typografia, atomy) i CSS Sekcji kontaktowej wtyczki, adresowane ścieżkami bezwzględnymi `/wp-content/...` — nginx serwuje je bez PHP.
- **[nwcezb]** Dane kontaktu w pliku to ręczna kopia sekcji `dane-kontaktu` — zmiana danych w sekcji wymaga tej samej zmiany w pliku, w kodzie.
- **[zf25m5]** Serwis nie powiadamia zespołu o błędach serwera; jedyny mechanizm — domyślny e-mail trybu odzyskiwania rdzenia WordPressa przy błędzie krytycznym PHP (na adres administratora witryny); 502, 504 i błąd bazy — bez powiadomienia. Pomysł: pomysly.md.

## Ikona witryny

- **[4qcyr9]** Ikona witryny — natywne ustawienie WordPressa „Ikona witryny" (`site_icon`): PNG 512×512 (czerwony sygnet Feuer na białym kwadracie) w bibliotece mediów, poza repozytorium; serwer dev ma własny załącznik. Wtyczka i motyw nie mają własnej obsługi ikony; WordPress generuje znaczniki `<link>` i adres `logo` danych strukturalnych ([seo.md](seo.md)).
- **[9gxxz5]** Znaczniki ikony (`rel=icon` 32×32 i 192×192, `apple-touch-icon`, `msapplication-TileImage`) wskazują rozmiary pośrednie AVIF — 32 → `ikona-witryny-150x150.avif`, 192, apple-touch-icon i 270 → `ikona-witryny-300x300.avif`: zapis rozmiarów pośrednich PNG jako AVIF ([media.md](media.md)) obejmuje także ikonę; w metadanych załącznika są tylko rozmiary 150 i 300.
- **[sx7tdf]** `/favicon.ico` — 302 na ikonę witryny (`ikona-witryny-150x150.avif`; HEAD — 200); routing vhosta: nginx.md, [ezx9gv].
- **[r3ymrv]** Ikonę na instancji ustawia się jak wybór w panelu: `wp media import` pliku, meta `_wp_attachment_context` = `site-icon`, rozmiary z filtrem `WP_Site_Icon::additional_sizes` (`wp_generate_attachment_metadata`), opcja `site_icon`.

## Typy stron pominięte

- **[v6bs3c]** E-commerce poza zakresem ([model-tresci.md](model-tresci.md), [kr68kr]); koszyk w headerze i „Dodaj do koszyka" z projektu nie weszły do serwisu; „Sprawdź całą ofertę e-sklepu" — wyłącznie etykieta linku (bez adresu) drugiej Karuzeli szkoleń we wzorcu strony głównej.
- **[wc5r4z]** Bez globalnej wyszukiwarki i stron wyników: header bez pola wyszukiwania; `/?s=` obsługuje szablon zapasowy `index` ([dr694q]; `noindex, follow`). Wyszukiwarki katalogu i listy artykułów to osobny mechanizm ([strony-zbiorcze.md](strony-zbiorcze.md), [baza-wiedzy.md](baza-wiedzy.md)).
- E-learning nie ma strony w serwisie: integracje.md, [8xu93a].
- Studium przypadku jako osobny typ strony — pomysł: pomysly.md.
