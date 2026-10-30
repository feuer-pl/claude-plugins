# Baza wiedzy

Strona Bazy wiedzy, lista artykułów i jej wyszukiwarka, strona artykułu (szablon), link i CTA produktu artykułu, spis treści. Model artykułów i ekspertów: [artykuly.md](artykuly.md); sekcja treści strony: [sekcje.md](sekcje.md); okruszki artykułu: [nawigacja.md](nawigacja.md); wyszukiwarka katalogu (ten sam mechanizm): [strony-zbiorcze.md](strony-zbiorcze.md).

## Strona Bazy wiedzy

- **[26ddda]** Baza wiedzy — natywna „strona z wpisami" (Ustawienia → Czytanie: `page_for_posts` = strona `baza-wiedzy`, ID 10) pod `/baza-wiedzy/`. Szablon `home`: header, okruszki (strona z wpisami jak zwykła strona), blok szablonowy `feuer/baza-wiedzy` (cały `<main>`), stopka.
- **[yfx5jg]** Treść strony — sekcja `baza-wiedzy` ([sekcje.md](sekcje.md), [7vmaes]), wyłącznie opublikowana, renderowana z kontekstem sekcji (jak w edytorze sekcji). Sekcja brak, nieopublikowana albo pusta (same białe znaki) — sama Lista artykułów (blok bez atrybutów).
- **[68jxc7]** Skład sekcji (treść początkowa): [README bloku `baza-wiedzy`](blok-baza-wiedzy.md), [xcfhp5]; redaktor składa własne bloki wokół listy.
- **[duy6fd]** H1 Top visualu w sekcji `baza-wiedzy` — [README bloku `top-kontentowy`](blok-top-kontentowy.md), [664zac]; bez ustawionej strony z wpisami — tytuł sekcji; edytowany w miejscu i zapisywany razem z sekcją (okno zapisu kilku elementów).
- **[mq8vt5]** Tytuł strony z wpisami jest H1 strony, tytułem karty przeglądarki strony wpisów i etykietą nad tytułem artykułu; okruszki i cel linku wstecz artykułu — [nawigacja.md](nawigacja.md), [dd2qsh], [gy9kmk].

## Lista artykułów

- **[sbw5zq]** Lista artykułów (`feuer/lista-artykulow`) działa w trybie Bazy wiedzy, gdy stoi w sekcji `baza-wiedzy` albo — poza edytorem — na stronie z wpisami: źródło stałe „wszystkie artykuły", atrybuty źródła ignorowane. Na innych stronach źródło wynika z atrybutów.
- **[7hpa25]** Lista jest zawsze w całości, bez stronicowania; adresy natywnego stronicowania strony z wpisami (`/baza-wiedzy/page/N/`, także N = 1, i `?paged=N`) zwracają 404 (filtr `pre_handle_404`, nagłówki bez cache).
- **[pa9m7g]** Dane listy (grupy, kolejność, tagi) liczy `feuer_lista_artykulow()` (`includes/baza-wiedzy.php`), blok tylko renderuje; dane Bazy wiedzy (produkt artykułu, powiązania produkt → artykuł, lista) są liczone raz na żądanie.
- **[4ajf4h]** Źródła: „wszystkie" — wszystkie artykuły, także bez produktu; „kategoria oferty", „branża", „TOP 20", „miesiące" — artykuły wskazane polem „Powiązany artykuł" przez opublikowane produkty źródła („TOP 20", „miesiące" — produkty z oznaczeniem „TOP 20" albo którymkolwiek z zaznaczonych miesięcy; „branża" — [taksonomie.md](taksonomie.md), [82fpks]); „wybór ręczny" — artykuły wskazane przez redaktora. Flaga „Nie pokazuj na listach artykułów": [artykuly.md](artykuly.md), [jwnmvv].
- **[u7xjw6]** Grupy (źródła „wszystkie", „branża", „TOP 20", „miesiące"): kategorie najwyższego poziomu oferty produktów wskazujących artykuł, w kolejności menu ([taksonomie.md](taksonomie.md), [xktvsv]), na końcu „Pozostałe" — artykuły bez kategorii (produkt bez kategorii; w źródle „wszystkie" także artykuł bez produktu); grupa bez artykułów nie jest pokazywana. Artykuł wskazany przez produkty z kilku grup stoi w każdej z nich.
- **[fht4rs]** Źródło „kategoria oferty": pierwsza grupa — sama kategoria (produkty przypięte bezpośrednio), dalej jej podkategorie (kolejność — [taksonomie.md](taksonomie.md), [xktvsv]; produkty podkategorii i jej potomków); bez grupy „Pozostałe". Wybór ręczny — jedna grupa bez nagłówka, w kolejności redaktora, tylko opublikowane, w bieżącym języku (także artykuły z flagą „Nie pokazuj na listach").
- **[kgk355]** Nagłówek grupy (H2): nazwa kategorii z liczbą artykułów całej grupy (bez nawiasów — mniejsza, szara, zwykła) i strzałką ↗ — link do strony kategorii; „Pozostałe" — bez linku.
- **[25z74v]** Kolejność w grupie (źródła automatyczne) — alfabetycznie po tytule (sortuje baza; kolacja `utf8mb4_unicode_520_ci` — litery z ogonkami jak litery podstawowe).
- **[mc9grv]** Pozycja: tytuł (H3, pogrubiony, bez znaczników HTML) — link do artykułu; lead — zajawka wpisana ręcznie (bez zajawki — bez leadu; nie jest generowany z treści), pełny tekst w HTML, widoczne najwyżej 2 wiersze z „…"; tagi branż. Pozycje stoją jedna pod drugą na szerokość kontenera (także na desktopie), rozdzielone linią.
- **[wbjzqs]** Tagi branż: branże wszystkich opublikowanych produktów wskazujących artykuł — zawsze wszystkie, w kolejności listy branż ([taksonomie.md](taksonomie.md), [4c6qy5]); sama nazwa, bez ikony i linku; artykuł bez branż — bez tagów; źródło „branża" — bez tagów. Grupy i tagi liczą się wyłącznie z produktów opublikowanych.
- **[kwfw7r]** Hover: nagłówek grupy i tytuł pozycji w kolorze marki; strzałka ↗ (sklejona z ostatnim słowem) widoczna tylko przy najechaniu, poza hoverem zajmuje miejsce — tekst nie skacze.

## Wyszukiwarka listy

- **[9c4vm6]** Pole wyszukiwania listy — wyłącznie na stronie Bazy wiedzy, w Top visualu kontentowym sekcji `baza-wiedzy` (bez pola w ustawieniach bloku; Lista artykułów na innych stronach i strona bez sekcji — bez pola); podpowiedź „Szukaj artykułu". Dwie kopie pola (wspólna fraza — [strony-zbiorcze.md](strony-zbiorcze.md), [4t2682]): od 1024 px na zdjęciu pod H1, poniżej 1024 px pod kartą, nad listą, na całą szerokość (widoczna jedna). W edytorze — wygląd jak na froncie, bez działania.
- **[s423rv]** Mechanizm jak wyszukiwarka katalogu ([strony-zbiorcze.md](strony-zbiorcze.md), [rtwzsy]). Pola dopasowania w atrybucie `data-szukaj` pozycji: tytuł (encje zdekodowane), potem lead w pełnym tekście — w grupie pozycje z dopasowaniem w tytule stoją przed dopasowaniem w leadzie.
- **[xqeyyu]** Przy wyszukiwaniu niepasujące pozycje i puste grupy są ukryte; liczba w nagłówku grupy się nie zmienia (liczba całej grupy); „Znaleziono: N" — liczba widocznych pozycji (artykuł w kilku grupach liczy się w każdej). Odstępy grup i linie pozycji liczą się od poprzedniej widocznej grupy albo pozycji.
- **[uhbnuy]** Brak wyników — komunikat jak w katalogu ([strony-zbiorcze.md](strony-zbiorcze.md), [e2afz8]), nad grupami.
- **[4ut5tb]** Fraza w adresie (`?q=`), wejście z `?q=` i × — jak w katalogu ([strony-zbiorcze.md](strony-zbiorcze.md), [n27npv], [ewhk98]).

## Strona artykułu

- **[bk79g2]** Artykuł — szablon `single`: header, blok szablonowy `feuer/artykul` (bez atrybutów; cały `<main>`, strona z danych bieżącego wpisu, okruszki w sekcji otwierającej), stopka.
- **[rdcyx9]** Skład: sekcja otwierająca → karta treści (pasek meta → „Ten artykuł dotyczy" przy produkcie → lead i spis treści → treść, przy produkcie z CTA w środku) → Sekcja kontaktowa → wizytówka autora (gdy ekspert ma opis).
- **[akn3q8]** Sekcja otwierająca: zdjęcie (obrazek wyróżniający; brak — obraz zastępczy, [artykuly.md](artykuly.md), [22bfx8]), na nim okruszki ([nawigacja.md](nawigacja.md), [jg6qr3]), etykieta kategorii z czerwoną linią — tytuł strony z wpisami („Baza wiedzy"; bez strony z wpisami — bez etykiety), H1 z tytułu wpisu. Karta treści nachodzi na zdjęcie; na mobile bez karty — pasek meta i spis treści na pełną szerokość.
- **[ek2w3u]** Pasek meta: czas czytania („N min czytania"), data publikacji (format `d.m.Y` jako string i18n), autor — imię i nazwisko eksperta, gdy wskazany i opublikowany (bez eksperta — bez autora); na mobile autor w drugim wierszu.
- **[wztmet]** Czas czytania liczony automatycznie z treści, bez CTA: liczba słów / 200 na minutę, zaokrąglona w górę, minimum 1.
- **[7zzx6g]** Lead — zajawka bez formatowania (klasa `is-style-wstep` jak styl „Lead"); pusta zajawka — bez leadu. Wiersz wstępu: od 1024 px lead i spis treści w dwóch kolumnach (lead z lewej); poniżej 1024 px (także tablet 640–1023 px) spis treści nad leadem na pełną szerokość, bez przewijania w poziomie. Bez H2 — bez spisu, bez zajawki — bez leadu, bez obu — bez wiersza wstępu.
- **[4hyurw]** Poniżej 1024 px rama ma wersję mobile (belka z hamburgerem; okruszki — [nawigacja.md](nawigacja.md), [jg6qr3]); poza wstępem i CTA w treści strona artykułu na tablecie ma układ desktopowy.
- **[w3n89e]** Wizytówka autora — poza kartą treści, w szarym boksie (na mobile bez tła): zdjęcie (opcjonalne; `loading="lazy"` — [media.md](media.md), [tewya3]), imię, opis; tylko gdy wskazany ekspert ma opis (zajawkę).
- **[232gbv]** Treść artykułu składa się z bloków palety treści ([paleta-tresci.md](paleta-tresci.md)), m.in. Ramka wyróżnienia, Cytat blokowy, Dwie kolumny.
- **[s3yrwk]** Linki spisu treści i „Sprawdź także" — w spoczynku kolor tekstu, hover w kolorze marki.

## Link i CTA produktu artykułu

- **[jxhfpc]** Artykuł z produktem ([artykuly.md](artykuly.md), [wbvxbp], [wbc8fy]): szablon renderuje z danych produktu link na początku, CTA w środku i Sekcję kontaktową na końcu — redaktor niczego nie wstawia w treść; teksty szablonu — [bloki.md](bloki.md), [8464y5].
- **[dncw7j]** Początek: na górze karty treści, nad leadem i spisem — blok z linią marki z boku na tle wyróżnionym: „Ten artykuł dotyczy: [tytuł wpisu produktu]" (pogrubiony; tytuł wpisu, nie nazwa skrócona), pod nim link akcji do strony produktu — szkolenie „Zobacz opis szkolenia", inny rodzaj „Zobacz opis produktu".
- **[yccmqr]** CTA w środku: przed H2 nr ⌊n/2⌋ + 1 treści (H2 liczone jak w spisie treści); przy mniej niż 2 H2 — bez CTA. Forma jak początek: tytuł wpisu produktu (pogrubiony), „Opis na karcie", zdanie wg stanu produktu i przycisk otwierający layer kontaktu z prewypełnieniem (formularz-kontaktu.md, [n4xfj4]); „Zamów" szkolenia gotowego do zapisu — formularz zapisu z najbliższym terminem (formularz-zapisu.md, [nrywje]). Od 1024 px przycisk z prawej, wyśrodkowany w pionie; poniżej — pod tekstem.

  | ID | Stan produktu | Zdanie | Przycisk |
  |---|---|---|---|
  | **[8b275w]** | szkolenie z aktualnym terminem | „Najbliższy termin szkolenia: [data, pogrubiona], [forma]." — data jak w Kalendarium („19 listopada 2026"), forma — etykieta słownika od małej litery; termin bez formy — samo zdanie z datą | „Zamów" (szkolenie, termin) |
  | **[9986kp]** | szkolenie bez aktualnego terminu | „Termin szkolenia dopasujemy do Twojej firmy." | „Uzgodnij termin" (szkolenie) |
  | **[458eaf]** | usługa, produkt bez rodzaju | „Porozmawiajmy o potrzebach Twojej firmy." | „Omówmy współpracę" (produkt) |

- **[x4hc6v]** Koniec: pod kartą treści, nad wizytówką autora — Sekcja kontaktowa z nagłówkiem i tekstem przycisku z sekcji `kontakt-artykulu` ([sekcje.md](sekcje.md), [uttbkn]; pusta albo brak — teksty domyślne bloku); przycisk prewypełnia layer kontaktu produktem artykułu.
- **[6t69aa]** Artykuł bez produktu: bez „Ten artykuł dotyczy" i CTA w środku; Sekcja kontaktowa bez prewypełnienia.

## Spis treści

- **[855g3e]** Spis treści — wyłącznie w szablonie artykułu, automatycznie z H2 treści (redaktor go nie układa), z pominięciem zdania belki zapowiedzi (`h2.belka-tytul`): blok spisu z tytułem „Spis treści" renderuje PHP tylko przy takim H2, pozycje buduje skrypt w przeglądarce — link-kotwica z ikoną i tekstem nagłówka, w kolejności treści.
- **[wkm8kb]** H2 bez `id` dostaje id ze sluga tekstu (małe litery, ł → l, bez znaków diakrytycznych, ciągi znaków spoza a-z0-9 → „-", bez „-" na brzegach); istniejące id zostaje. Klik — natywna kotwica, płynne przewinięcie daje `scroll-behavior: smooth`. Ikonę pozycji wskazuje atrybut `data-ikona` spisu (adres ikony z HTML renderu).
