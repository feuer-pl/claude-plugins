# Uprawnienia

Role i konta, blokady edycji („idiotoodporność"), bloki dostępne w edytorze, Site Editor, dane kont i REST bez logowania. Uprawnienia poszczególnych obiektów — sekcja „Edycja i uprawnienia" dokumentów [produkt.md](produkt.md), [artykuly.md](artykuly.md), [sekcje.md](sekcje.md), [ustawienia.md](ustawienia.md); uprawnienia termów — [taksonomie.md](taksonomie.md), „Wspólne" ([52n8r5]).

## Blokady edycji

- **[dmg2yg]** Zasada: redaktor jest nietechniczny — system nie pozwala mu psuć układu, ale zamek jest rozsądny, nie totalny. Realizują ją blokady z tej sekcji, blokady sekcji ([sekcje.md](sekcje.md)) i paleta treści.
- **[uktfp5]** `theme.json` motywu wyłącza narzędzia wyglądu (`appearanceTools: false`) i wszystkie ustawienia stylu w edytorze: kolory (palety, gradienty, duotony, kolory elementów), typografię (rozmiary, kroje, interlinia, odstęp liter, dekoracje, kolumny tekstu, kierunek pisania, inicjał), odstępy (padding, margines, `blockGap`), obramowania, cienie, wymiary, pozycję przyklejoną, tło, lightbox i edycję układu; listy motywu (palety, kroje, rozmiary, odstępy, cienie) są puste.
- **[mvnadz]** Blokada struktury tam, gdzie ma być stała: pełna blokada sekcji z jednym blokiem pól (bez odblokowania — [sekcje.md](sekcje.md)); bloki z atrybutem `lock` (bez przesuwania i usuwania) — w menu bloku zostają „Odblokuj" i „Ukryj".
- **[ffm7nk]** Typy wpisów nie mają `template_lock` — redaktor przestawia i usuwa bloki w treści (np. produktu).

## Bloki w edytorze

- **[tpzesj]** Whitelisty bloków per typ wpisu nie ma: edytor każdego typu wpisu oferuje te same bloki (poza ukrytymi we wstawiaczu — `inserter: false` — i dostępnymi wyłącznie w bloku nadrzędnym — `parent`), a blok „własny HTML" (`core/html`) ma także redaktor (rola `editor` ma `unfiltered_html`). Zakres palety treści: [paleta-tresci.md](paleta-tresci.md), [8psccg].

## Site Editor

- **[cr9xjt]** Redaktor nie ma dostępu do Site Editora — domyślna rola `editor` nie ma `edit_theme_options`; kod tego nie zmienia.
