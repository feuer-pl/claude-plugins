# Artykuły

Artykuły Bazy wiedzy (natywne wpisy `post`) i ich autorzy (typ `ekspert`): pola, flaga list, produkt artykułu. Produkt: [produkt.md](produkt.md); przegląd modelu: [model-tresci.md](model-tresci.md).

## Artykuł (`post`)

- **[s3cs3w]** Artykuły Bazy wiedzy to natywne wpisy `post` (adres — [strony.md](strony.md), [gsgh6b]; strona z wpisami — [baza-wiedzy.md](baza-wiedzy.md), [26ddda]). Szablon wpisu składa blok `feuer/artykul`.
- **[63d2wt]** Typ publiczny, w REST (`posts`), bez archiwum typu; obsługuje tytuł, treść, obrazek wyróżniający, zajawkę, pola własne i formaty wpisu — bez autora WP.
- **[x4mpxw]** Pozostałe rodzaje treści Bazy wiedzy (studium przypadku, wzór dokumentu, publikacja) nie mają modelu w serwisie.

### Pola

| ID | Pole | Klucz | Typ i wartości | Dozwolone | Wymagane / domyślne | Uwagi |
|---|---|---|---|---|---|---|
| **[ypnggk]** | Tytuł | natywny | tekst | tekst jednowierszowy, bez formatów | wymagane | H1 artykułu |
| **[yasdst]** | Zajawka | natywny `excerpt` | tekst | tekst z łamaniem wiersza, bez formatów | | lead artykułu |
| **[3s5yhq]** | Obrazek wyróżniający | natywny | ID załącznika | medium: obraz | brak = obraz zastępczy motywu | zdjęcie artykułu |
| **[g4srzk]** | Autor artykułu | `_feuer_ekspert` | ID wpisu `ekspert` (liczba całkowita) | wybór | 0 = bez autora; nieobowiązkowe | |
| **[mmyhvc]** | Nie pokazuj na listach artykułów | `_feuer_bez_listy` | tak / nie | przełącznik | nie | |

- **[587wxx]** Meta `_feuer_ekspert` i `_feuer_bez_listy` są w REST; zapis — [uprawnienia.md](uprawnienia.md), [pgxvxr].
- **[zxj2pt]** Artykuł ma też pola SEO — „Tytuł dla wyszukiwarek" (`_feuer_seo_tytul`) i „Opis dla wyszukiwarek" (`_feuer_seo_opis`): [seo.md](seo.md), „Pola nadpisania".
- **[22bfx8]** Obraz zastępczy artykułu bez obrazka wyróżniającego — plik motywu `feuer-skorka/img/artykul-zapasowy.jpg` (JPEG 633×553), poza biblioteką mediów, wstawiany z `width` i `height`; jedna funkcja (`feuer_zdjecie_artykulu()`) dla otwarcia artykułu (`eager`, `fetchpriority="high"`) i bloku Aktualności (`lazy`).

### Relacje

- **[zcwww4]** Autor artykułu = wpis `ekspert`; ID jest rozwiązywane na tłumaczenie eksperta ([wielojezycznosc.md](wielojezycznosc.md), [kyvf24]).
- **[wbvxbp]** Produkt artykułu: opublikowany produkt, którego pole „Powiązany artykuł" (`_feuer_artykul`) wskazuje ten artykuł; przy kilku — najwcześniej opublikowany (przy równej dacie — niższe ID); w bieżącym języku ([wielojezycznosc.md](wielojezycznosc.md), [kyvf24]). Artykuł nie przechowuje produktu.
- **[wbc8fy]** Produkt artykułu zasila okruszki, link do produktu („Ten artykuł dotyczy") i CTA w szablonie artykułu.

### Edycja i uprawnienia

- **[qacp6t]** Edytor wpisu nie pokazuje autora WP (typ bez obsługi `author`) ani wiersza „Szablon" (`supportsTemplateMode` wyłączone; wpis ma jeden szablon motywu); zajawka zostaje — jest leadem.
- **[azuzdc]** Autora wybiera się w panelu bocznym „Autor artykułu" edytora wpisu.
- **[a3cg2z]** Flagę ustawia się w panelu bocznym „Widoczność na listach" edytora wpisu.
- **[ht9pkv]** Typografia treści w edytorze wpisu — css.md, [h8kha9]; pole tytułu ma typografię H1 artykułu (wspólna reguła).
- **[npkmr3]** Artykuł i eksperta zakłada się i zmienia także z czatu — operacje artykułu i eksperta oraz operacje treści (cms-z-czatu.md, „Operacje artykułu i eksperta", „Operacje treści"), w granicach uprawnień konta; ekspert założony z czatu powstaje opublikowany (cms-z-czatu.md, [bz3z46]).

### Odbiorcy

- **[jwnmvv]** Flaga „Nie pokazuj na listach artykułów" wyłącza artykuł ze wszystkich list automatycznych artykułów: Lista artykułów (każde źródło poza wyborem ręcznym) i Aktualności; wybór ręczny może go wskazać. Na listach jest artykuł bez klucza meta albo z wartością inną niż „1". Flaga dotyczy wyłącznie list w serwisie: artykuł zostaje pod swoim adresem, bez `noindex`, w sitemapie i w kanale RSS; ukrycia pojedynczego artykułu przed wyszukiwarką serwis nie ma.
- **[srd8za]** Kanał RSS wpisów: 10 ostatnich artykułów (`posts_per_rss`), pełna treść (`rss_use_excerpt` = 0).

## Ekspert (`ekspert`)

- **[nj5yv8]** Ekspert — autor artykułu, byt niezależny od kont WP: imię i nazwisko = tytuł, zdjęcie = obrazek wyróżniający, opis = zajawka; bez edytora treści (ekran edycji klasyczny).
- **[bwmjb6]** Typ niepubliczny — bez adresów na froncie i niewidoczny na froncie; pozycja „Eksperci" w menu panelu; w REST; domyślne uprawnienia wpisów — redaktor tworzy, edytuje, publikuje i usuwa ekspertów.

## Wielojęzyczność

- **[jsxder]** Artykuły (`post`) są tłumaczone; ID artykułu i produktu artykułu rozwiązywane na wpis w bieżącym języku — [wielojezycznosc.md](wielojezycznosc.md), [n7fr7r], [kyvf24].
