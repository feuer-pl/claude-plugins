# Wzorce stron

Wzorce stron wtyczki — gotowe składy bloków, które redaktor i agent wstawiają i wypełniają zamiast składać stronę z pamięci — oraz mapowanie pięter szablonu treści produktu na bloki. Bloki: [bloki.md](bloki.md); zestawy startowe sekcji kategorii i branży: [sekcje.md](sekcje.md).

## Rejestracja

- **[jq5v4a]** Wzorce stron mają własną kategorię wstawiacza „Strony" (slug `feuer-strony`), rejestrowaną przez wtyczkę; nazwa i tytuły wzorców — przez i18n.
- **[qfnn5n]** Wzorzec = plik `wzorce/<nazwa>.html` ze statycznym markupem bloków, rejestrowany w `includes/wzorce.php` (`register_block_pattern`: `title`, `categories` = `feuer-strony`, `postTypes` — typ wpisu, `filePath`; wzorce produktu — pętla w `feuer_wzorce_stron()`); plik jest czytany dopiero, gdy edytor pobiera wzorzec.
- **[8z7gav]** Treść wzorca nie zawiera ID mediów, wpisów ani termów: zdjęcia puste (obraz zastępczy), linki z samą etykietą (znacznik `<wprowadź link>`) — zdjęcia i adresy redaktor ustawia po wstawieniu.
- **[t24ct2]** Wzorzec startowy (`blockTypes: core/post-content`) pojawia się w oknie wyboru wzorca przy nowym, pustym wpisie swojego typu; po wstawieniu to zwykła treść wpisu, bez związku z wzorcem. Typy wpisów nie mają `template_lock` ([uprawnienia.md](uprawnienia.md), [ffm7nk]).

| ID | Wzorzec | Slug | Typ wpisu | Startowy |
|---|---|---|---|---|
| **[es7gvq]** | Strona główna | `feuer/strona-glowna` | `page` | nie — wstawiany ze wstawiacza |
| **[aewuqh]** | Strona kontentowa | `feuer/strona-kontentowa` | `page` | tak |
| **[bu9r6e]** | Szkolenie, Usługa | `feuer/produkt-szkolenie`, `feuer/produkt-usluga` | `produkt` | tak — redaktor wybiera jeden przy tworzeniu produktu |

- **[hegdab]** Innych wzorców nie ma: strony filarów, strona „Oferta", strony lądowania i pozostałe strony nie mają własnego wzorca — składa się je z bloków. Wzorzec „Strona kontentowa" jest dostępny dla każdej strony (`page`) i daje Top visual kontentowy (poza wstawiaczem) — nową stronę z tym blokiem (kontentową, filaru, lądowania) zaczyna się od niego.

## Strona główna

- **[t239y7]** Skład, kolejno: Karty informacyjne na zdjęciu w odmianie hero, Belka zapowiedzi (bez atrybutów — dane z sekcji `belka-zapowiedzi`), Karuzela szkoleń, Kafelki branż, Karuzela szkoleń, Kalendarium, Belka informacyjna (odmiana 1, przycisk bez adresu), Aktualności.
- **[x2fye7]** Hero: `hero: true`, pas 21:9, cztery karty bez linków.
- **[t9dk64]** Pierwsza Karuzela szkoleń: odmiana ciemna, źródło „TOP 20", limit „wszystkie" (`limit` 0); druga — bez ustawień (domyślne bloku: [README karuzela-szkolen](blok-karuzela-szkolen.md), [jdw88w], [e3ts8k], [9yvuqs]).
- **[486erf]** Sekcja „Nie wiedziałem…" to Kalendarium (nie Terminy): nagłówek w całości w polu `tytul`, bez leadu; przyciski kart puste — teksty domyślne bloku ([README kalendarium](blok-kalendarium.md), [z5m6uw], [p9nznu]).
- **[nex42x]** Pola bloków treściowych mają teksty z projektu strony głównej (łamania wierszy jak w projekcie, akcenty — [bloki.md](bloki.md), „Zestawy formatów"); zdjęcia puste; bloki z danych pokazują dane instancji.
- **[s3bf76]** Markup wzorca jest w kanonicznej serializacji bloków (architektura-kodu.md, [2ue5ax], [rs3jpt]) — `parse_blocks` / `serialize_blocks` nie zmieniają treści, edytor nie zgłasza błędu bloku.

## Strona kontentowa

- **[3pz3w9]** Jeden blok: Top visual kontentowy z blokadą przesuwania i usuwania (`lock`); po wyborze w karcie jeden pusty akapit. Wzorzec wspólny dla wielu stron — dalszy skład redaktor dodaje sam.

## Strona produktu

- **[k7wy5j]** Pola tekstowe wzorców produktu są puste (bloki pokazują znaczniki pól obowiązkowych i teksty domyślne) — poza nagłówkiem Terminów (równym domyślnemu) i etykietami przycisków belek we wzorcu „Szkolenie" ([u4jun9]); bloki wewnętrzne bez atrybutów — poza nadtytułami etapów Programu „1."–„4."; resztę uzupełniają szablony bloków przy wstawieniu (np. odpowiedź FAQ).
- **[m9behp]** Skład wzorców:

| Blok | Ustawienia | Szkolenie | Usługa |
|---|---|---|---|
| Top visual produktowy | blokada przesuwania i usuwania | tak | tak |
| Kluczowe informacje | wariant „tabela z danych" | tak | — |
| Terminy | źródło „bieżące szkolenie", nagłówek „Terminy otwartych szkoleń" (= domyślny) | tak | — |
| Dla kogo | 5 pozycji | tak | tak |
| Karty informacyjne na zdjęciu | 4 karty | tak | tak |
| Karta opisu produktu (Program) | 4 etapy, nadtytuły „1."–„4." | tak | tak |
| Belka informacyjna | odmiana 2 | tak | tak |
| 2 × nagłówek H3 + akapit | zwykła treść z palety, na szerokości kontenera treści | tak | tak |
| Proces współpracy | 4 kroki | tak | tak |
| Karty informacyjne na zdjęciu | 5 kart | tak | tak |
| Belka informacyjna | odmiana 1 | tak | tak |
| FAQ | 1 pytanie | tak | tak |
| Sekcja kontaktowa | bez atrybutów (teksty domyślne, dane kontaktu z sekcji) | tak | tak |
| Zobacz także | domyślne (powiązania produktu, nagłówek domyślny) | tak | tak |

- **[u4jun9]** Wzorzec „Szkolenie": przyciski obu belek — „Zamów szkolenie", cel „zamówienie produktu" (`zamowienie: true` — layer kontaktu z prewypełnieniem). Wzorzec „Usługa": belki bez przycisku (obowiązkowy przycisk pokazuje znacznik).
- **[u3zw36]** Wzorce produktu nie zawierają Opinii klienta (`feuer/cytat`) — redaktor wstawia ją, gdy ma prawdziwy cytat.
