# Sekcje

Typ wpisu `sekcja` — redagowalne fragmenty stron systemowych i ramy strony (header, stopka, nagłówki stron kategorii i branż, teksty globalne bloków), wstawiane po slugu. Przegląd modelu: [model-tresci.md](model-tresci.md); uprawnienia: [uprawnienia.md](uprawnienia.md).

## Typ wpisu

- **[dquuyy]** Treść ramy strony i fragmentów stron systemowych żyje w sekcjach; sekcję wskazuje się slugiem (nie ID i nie wzorcem `wp_block`, którego ID zależy od bazy).
- **[sped82]** Typ niepubliczny: bez adresów na froncie i poza wyszukiwaniem; pozycja „Sekcje" w menu panelu; edytor blokowy; w REST.
- **[2kdpjq]** Obsługuje tytuł, treść, obrazek wyróżniający (zdjęcie Top visualu kontentowego w sekcji branży) i pola własne.
- **[8vsg6f]** Header i stopka to części szablonu motywu (`naglowek`, `stopka`), które tylko wstawiają sekcję po slugu blokiem `feuer/sekcja` (`naglowek-serwisu`, `stopka-serwisu`).

## Zestaw sekcji

| ID | Slug | Treść | Tworzenie | Chroniona | Pełna blokada struktury |
|---|---|---|---|---|---|
| **[2ysenk]** | `naglowek-serwisu` | header serwisu: blok `feuer/naglowek` z blokadą przesuwania i usuwania | administrator | tak | nie |
| **[78a65y]** | `stopka-serwisu` | stopka serwisu: blok `feuer/stopka` z blokadą przesuwania i usuwania | administrator | tak | nie |
| **[yyq58q]** | `belka-zapowiedzi` | dane belki zapowiedzi: blok `feuer/belka-zapowiedzi-dane` | administrator, treść = przykład z README bloku `belka-zapowiedzi-dane` | nie | tak |
| **[96pxac]** | `terminy-brak` | teksty stanu pustego bloku Terminy | administrator, WP-CLI z README bloku `terminy-brak` | nie | tak |
| **[4t826x]** | `dane-kontaktu` | „Dane kontaktu" — dane kontaktu karty Sekcji kontaktowej, jeden tekst formatowany (blok wewnętrzny) | administrator, WP-CLI z README bloku `dane-kontaktu` | nie | tak |
| **[apz8vx]** | `zgoda-rodo` | treść zgody RODO layeru kontaktu (blok wewnętrzny) | administrator, WP-CLI z README bloku `zgoda` | nie | tak |
| **[mapthe]** | `kontakt-kategorii` | nagłówek i tekst przycisku Sekcji kontaktowej stron kategorii | administrator | nie | tak |
| **[uttbkn]** | `kontakt-artykulu` | nagłówek i tekst przycisku Sekcji kontaktowej artykułów | administrator | nie | tak |
| **[7vmaes]** | `baza-wiedzy` | treść strony Bazy wiedzy | administrator (Sekcje → Dodaj albo WP-CLI z README bloku `baza-wiedzy`) | nie | nie |
| **[p3zcgm]** | `kategoria-<slug termu>` | nagłówek strony kategorii oferty: zablokowany Top visual listingu i bloki redaktora pod nim | automatycznie przy utworzeniu termu `oferta` | nie | nie |
| **[wcbkbp]** | `branza-<slug termu>` | treść strony branży: zestaw startowy i bloki redaktora | automatycznie przy utworzeniu termu `branza` | nie | nie |

- **[rrzbuy]** Sekcje stałe (wszystkie poza `kategoria-*` i `branza-*`) nie powstają automatycznie — na każdym środowisku tworzy je administrator; treść początkowa i polecenie WP-CLI — README bloków `belka-zapowiedzi-dane`, `terminy-brak`, `dane-kontaktu`, `zgoda`, `baza-wiedzy`; `naglowek-serwisu` i `stopka-serwisu` — przykład bloku w README bloków `naglowek` i `stopka`; `kontakt-kategorii` i `kontakt-artykulu` — README bloku `sekcja-kontaktowa` (brak sekcji = Sekcja kontaktowa z tekstami domyślnymi).
- **[jjssnu]** Blok sekcji widzi wyłącznie sekcję opublikowaną; szkic, wpis oczekujący albo prywatny = brak sekcji.

## Sekcje kategorii i branż

- **[cvg94e]** Utworzenie termu `oferta` tworzy kodem (niezależnie od tego, kto utworzył term) opublikowaną sekcję `kategoria-<slug termu>` o tytule „Kategoria: <nazwa>" z blokiem Top visual listingu zablokowanym (bez przesuwania i usuwania); redaktor dopisuje pod nim własne bloki.
- **[zjsw2g]** Utworzenie termu `branza` tworzy kodem (niezależnie od tego, kto utworzył term) opublikowaną sekcję `branza-<slug termu>`; tytuł = nazwa branży (H1 Top visualu kontentowego), z encjami HTML zdekodowanymi (nazwa termu jest zapisana z encjami, np. `&amp;`).
- **[8h54zx]** Zestaw startowy sekcji branży: Top visual kontentowy (zablokowany; etykieta = nazwa branży; karta: H2 „Dlaczego Feuer", dwie kolumny, przyciski „Skontaktuj się z nami" i „Zobacz pełną ofertę"), Kafle produktowe (zablokowane, źródło „branża bieżącej strony", kafel kontaktowy), Belka informacyjna odmiany 1 („Tygodnie Bezpieczeństwa", przycisk „Przeczytaj o współpracy"), Kalendarium; puste pola wypełnia redaktor.
- **[2zm4t5]** Przyciski zestawu startowego sekcji branży nie mają adresów — wpisuje je redaktor.
- **[ta89qw]** Teksty zestawu startowego i tytuł sekcji kategorii — przez i18n, w języku, w którym utworzono term.
- **[9nam3d]** Istniejąca sekcja o tym samym slugu zostaje bez zmian — kod nie tworzy drugiej.
- **[57skqj]** Sekcja powstaje wyłącznie przy utworzeniu termu: termy sprzed mechanizmu jej nie mają (fallback strony termu); zmiana nazwy albo sluga termu i usunięcie termu nie zmieniają ani nie usuwają sekcji — po zmianie sluga strona termu szuka sekcji po nowym slugu.
- **[4mgma2]** Sekcje branż dla istniejących termów tworzy polecenie WP-CLI z README bloku `branza`.

## Edycja i uprawnienia

- **[fmx868]** Zestaw sekcji jest zamknięty: tworzenie i usuwanie — wyłącznie administrator (`manage_options`); edycja — uprawnienia do stron (`edit_pages` itd.), więc redaktor edytuje istniejące sekcje.
- **[etwwzs]** Sekcja chroniona (kolumna „Chroniona"; meta `_feuer_sekcja_chroniona` = tak) — edycja wyłącznie dla administratora (`map_meta_cap`); pozostałe sekcje edytuje redaktor.
- **[vrh5ga]** Meta `_feuer_sekcja_chroniona`: tak / nie, w REST; brak wartości = niechroniona; zapis wyłącznie administrator. Ustawia ją pole „Ochrona sekcji" („Edycja wyłącznie dla administratora") w panelu bocznym edytora sekcji, widoczne tylko dla administratora; zapis pola — z poprawnym nonce i `manage_options`, odznaczone = niechroniona.
- **[ytey65]** Sekcje z „tak" w kolumnie „Pełna blokada struktury" mają w edytorze pełną blokadę struktury (bez dodawania, przesuwania i usuwania bloków); edytor nie oferuje odblokowania. Redaktor zmienia wyłącznie pola bloku (w danych kontaktu i zgodzie — bloki wewnętrzne).
- **[p9yhm6]** Pełna blokada obejmuje wyłącznie sekcje z listy slugów w kodzie; nowa sekcja globalna poza listą nie jest blokowana.

## Wielojęzyczność

- **[e4jhpt]** Sekcja po slugu przechodzi przez abstrakcję tłumaczeń (`feuer_wpis_w_biezacym_jezyku()`, dziś przechodnia — [wielojezycznosc.md](wielojezycznosc.md), [bacp9q]); typ `sekcja` nie jest tłumaczony ([8bcbuy]), więc każda wersja językowa strony renderuje sekcję PL. Przekierowanie na wersję domyślną (stan planowany) dotyczy wyłącznie stron: sekcja jest fragmentem strony, więc brak tłumaczenia jednego fragmentu nie wyłącza wersji językowej.
- **[8bcbuy]** Typ `sekcja` nie jest tłumaczony w Polylang — sekcje nie mają wersji językowych.
