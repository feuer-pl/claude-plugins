# Strony zbiorcze

Strony z listami produktów: „Oferta", strony kategorii oferty, strony branż, strony filarów; karta i grupa produktów, widoczność i kolejność. Taksonomie: [taksonomie.md](taksonomie.md); pola produktu: [produkt.md](produkt.md); źródła pozycji bloków: [bloki.md](bloki.md); sekcje stron: [sekcje.md](sekcje.md); okruszki i menu: [nawigacja.md](nawigacja.md).

## Strony

- **[nfjfhw]** Strony kategorii oferty i strony branż to strony systemowe ([strony.md](strony.md), [bj92ag]); ręcznych stron kategorii nie ma — adres `/oferta/<slug>/` obsługuje wyłącznie archiwum termu, bez nadpisania termu zwykłą stroną.
- **[rn6a9b]** Strony zbiorcze niezwiązane z taksonomią („Oferta", strony filarów, strony lądowania) to zwykłe strony (`page`) składane ręcznie z bloków — top visual i źródła list wybiera redaktor.
- **[tzvztg]** Adresy kategorii i branż — [taksonomie.md](taksonomie.md), [u9pkpc], [wkeeu2]; reguły adresów obejmują także kanał, `embed` i strony (`/page/N/`).

## Karta produktu

- **[kejzfv]** Jedna karta produktu we wszystkich listach stron zbiorczych (Kafle produktowe, listingi kategorii i branż, wyniki wyszukiwarki): jedna funkcja renderu (`feuer_karta_produktu()` z wpisu, `feuer_karta_produktu_html()` z danych — także przykład bloku) i jeden CSS (`css/kafle-produktowe.css`). To inna karta niż pozycja „Zobacz także" i karta Karuzeli szkoleń.
- **[jxa6mt]** Cała karta — pozycja `<li>` siatki — jest jednym linkiem do produktu: zdjęcie (obrazek wyróżniający; dekoracyjne — pusty `alt`; zawsze `loading="lazy"`, także w pierwszym ekranie; rozmiar `full` z `sizes` 100vw / 50vw / 25vw dla < 640 / < 1024 / ≥ 1024 px), tag produktu na zdjęciu (gdy ustawiony), nazwa na karcie ([produkt.md](produkt.md), [hh6g67]), „Opis na karcie", strzałka ↗ (dekoracyjna).
- **[3dh7tn]** Produkt bez obrazka wyróżniającego — stan „bez zdjęcia" z projektu (jasny szary pod nakładką ze znakiem Feuer, klasa `.bez-zdjecia`), nie obraz zastępczy (wyjątek od reguły pól obowiązkowych): na karcie, w Top visualu produktowym i w Zobacz także (README bloków). Zdjęcie produktu zostaje obowiązkowe — produkty nie mają zdjęcia domyślnego.
- **[ctq2h9]** Nazwa na karcie — nagłówek h3; wywołujący może zmienić poziom (strona kategorii — h2, bo nad kartami jest tylko H1); wygląd bez zmian.
- **[5ad8gf]** „Opis na karcie" (`_feuer_opis_karty`) jest obowiązkowy ([bloki.md](bloki.md), [myhuw8]); niepusty — w całości, bez ucinania (na desktopie 80 znaków to do 3 wierszy), zwykłym tekstem.
- **[sgryau]** Hover: część tekstowa karty w kolorze marki z białym tekstem, strzałka ↗ zmienia się w →; na szarym tle bloku karta jest biała.
- **[vjmjws]** Tag produktu z kodu `_feuer_tag`: odmiana (klasa), symbol ikony ze sprite'a i nazwa ze słownika (i18n) — „Wymagane prawem": `tag-wymog-prawny`, `i-waga`; „Nowość": `tag-nowosc`, `i-megafon`; „Zmiana przepisów": `tag-zmiana-przepisow`, `i-ksiazka`; „Ważne teraz": `tag-wazne-teraz` (pigułka neutralna), `i-megafon`. Pusty albo nieznany kod — bez tagu.

## Grupa produktów

- **[ty4cwk]** Grupa = nagłówek H2 + wprowadzenie + siatka kart; jedna funkcja (`feuer_grupa_produktow()`) dla bloku Kafle produktowe, listingu kategorii i listingu branży — grupy różnią się wyłącznie źródłem pozycji; szablony stron kategorii i branży wywołują ten sam render ze źródłem z taksonomii. Nagłówek i wprowadzenie opcjonalne (bez nagłówka — sama siatka; puste wprowadzenie nie jest renderowane); wprowadzenie — treść redakcyjna w typografii treści; na końcu siatki opcjonalny dodatek (kafel kontaktowy) jako pozycja `<li>`; grupa bez kart nie wyświetla się. Funkcja nie oczyszcza nagłówka ani wprowadzenia — HTML oczyszcza wywołujący.
- **[93h2pr]** Siatka kart: 4 kolumny na pełnej szerokości kontenera (karta = 3 kolumny siatki 12), 3 obok drzewa kategorii, na tablecie 2, na telefonie 1.

## Widoczność i kolejność

- **[hu253v]** Listy automatyczne produktów (`feuer_produkty_listingu()`): opublikowane produkty (także bez rodzaju) bez flagi „Nie pokazuj w listingu kategorii" ([produkt.md](produkt.md), [999uaf]; brak meta albo wartość różna od 1), spełniające warunek taksonomii wywołującego (kategoria, branża, oznaczenia), w języku strony ([wielojezycznosc.md](wielojezycznosc.md), [4htqwa]); bez limitu i stronicowania, w kolejności listingu; dane produktów i miniatur wczytywane hurtem. Ta sama lista daje TOP 20 (oznaczenie `top-20`).
- **[xbcyrc]** Kolejność listingu (`feuer_kolejnosc_listingu()`): najpierw produkty z Promocją lub Nowością, w obu grupach ranga rosnąco (1 najwyżej, bez rangi na końcu), przy równej randze — nazwa na karcie porównywana bajtowo (wielkie litery przed małymi, litery z polskimi znakami po wszystkich literach ASCII); ta sama kolejność — wiersze bloku Terminy szkoleń otwartych. Listy ręczne — kolejność redaktora.
- **[g62a6w]** Kategoria „ma produkty" (`feuer_oferta_ma_produkty()`; kafle kategorii, drzewo kategorii), gdy w niej albo w jej podkategoriach jest opublikowany produkt bez flagi „Nie pokazuj w listingu kategorii".

## Strona „Oferta"

- **[fd2mvb]** Strona „Oferta" (`/oferta/`) — zwykła strona: Top visual listingu, Kafle kategorii (kategorie najwyższego poziomu z produktami widocznymi w listingu), Sekcja kontaktowa. Produkt bez kategorii oferty nie pojawia się na niej.

## Strona kategorii

- **[as989d]** Szablon `taxonomy-oferta`: header, blok szablonowy `feuer/kategoria` (cały `<main>`), stopka; okruszki — [nawigacja.md](nawigacja.md), [xmubhb]. `<main>` ma klasę treści strony ([strony.md](strony.md), [uzqjqk]).
- **[8c5wty]** Skład: na górze sekcja `kategoria-<slug termu>` (opublikowana; brak albo pusta — Top visual listingu z danymi termu i zdjęciem w tle do 1920 px (css.md, [k34pyh]): [sekcje.md](sekcje.md), [p3zcgm]); listing — drzewo kategorii po lewej, kafle podkategorii i karty po prawej; na dole sekcja `kontakt-kategorii` (jedna dla wszystkich stron kategorii, struktura zablokowana — [sekcje.md](sekcje.md), [mapthe]; brak albo pusta — Sekcja kontaktowa z tekstami domyślnymi).
- **[f49aqa]** Węzeł drzewa — jedna reguła dla każdego poziomu: kafle bezpośrednich podkategorii (kolejność — [taksonomie.md](taksonomie.md), [xktvsv]; tylko z produktami widocznymi w listingu), pod nimi osobną sekcją, bez nagłówka, produkty przypięte bezpośrednio do termu (produkty podkategorii są na ich stronach); węzeł bez dzieci — sama siatka produktów; bez kafli i produktów — komunikat „W tej kategorii nie ma jeszcze produktów." z linkiem „Skontaktuj się z nami" (layer kontaktu, i18n). Bez stronicowania i „Pokaż więcej" — wszystkie kafle i karty naraz.
- **[w2e94j]** Drzewo kategorii (panel „Kategoria"): kategorie najwyższego poziomu i ich bezpośrednie podkategorie (głębszych nie; kolejność — [taksonomie.md](taksonomie.md), [xktvsv]); kategorie bez produktów pominięte na każdym poziomie (także na stronie pustej kategorii). Nazwa — link do strony kategorii; kategoria z podkategoriami ma przycisk ˅ / ˄ rozwijający je w miejscu (`data-rozwijane="akordeon"`, etykieta „Podkategorie: <nazwa>"; każda niezależnie), bez podkategorii — strzałka › w linku; podkategoria — link. Od startu rozwinięta i wyróżniona (kolor marki z linią) jest kategoria najwyższego poziomu bieżącego termu; pozycja bieżącej strony ma `aria-current="page"` (kolor marki).
- **[dswdfq]** Układ: od 1024 px drzewo zajmuje 3 kolumny siatki, pozycje — 9 (karty po 3 w rzędzie); poniżej 1024 px bez drzewa (nawigacja przez menu i link „Wstecz"), kafle podkategorii w jednej kolumnie; kolumny kart — [93h2pr].
- **[47wr84]** Kafel kategorii (strona kategorii i blok Kafle kategorii — ta sama funkcja `feuer_kafel_kategorii()`): jeden link do strony kategorii — zdjęcie termu (`_feuer_zdjecie`; brak — stan „bez zdjęcia"), ikona termu (`_feuer_ikona`; brak — sama nazwa), nazwa, strzałka ↗; zdjęcie i ikona dekoracyjne (pusty `alt`); zdjęcie w rozmiarze `full` z `sizes` 100vw do 1023 px, powyżej 27vw; ikona `full` bez `sizes`; bez atrybutu `loading` (heurystyka WordPressa).
- **[n7rpch]** Top visual listingu w trybie kategorii (archiwum termu `oferta` albo sekcja `kategoria-<slug>` istniejącego termu): H1 — nazwa termu; lead — opis termu (łamania wierszy → `<br>`, dozwolone `strong` i `br`; pusty — bez leadu); zdjęcie termu, brak — zdjęcie kategorii bezpośrednio nadrzędnej (jeden poziom), brak obu — stan „bez zdjęcia". Pola bloku są ignorowane, w edytorze bez edycji — dane zmienia się w termie.

## Strona branży

- **[8989ej]** Szablon `taxonomy-branza` („Strona branży"): header, okruszki, blok `feuer/branza` (cały `<main>`, klasa `strona-branzy`; klasa treści strony — [strony.md](strony.md), [uzqjqk]), stopka.
- **[4bbc9p]** Treść — sekcja `branza-<slug termu>` ([sekcje.md](sekcje.md), [wcbkbp]), opublikowana, rozwiązywana przez abstrakcję tłumaczeń (dziś zawsze PL). Bloki dostają kontekst sekcji (`postId`, `postType` = `sekcja`): Top visual kontentowy i Kafle produktowe ze źródłem „branża bieżącej strony" czytają z niego dane ([README top-kontentowy](blok-top-kontentowy.md), [664zac], [n38er8]; [README kafle-produktowe](blok-kafle-produktowe.md), [mbmw3z]). Sekcja brak, nieopublikowana albo pusta (same białe znaki) — sam listing: Kafle produktowe ze źródłem „branża" (branża termu), pusty nagłówek (znacznik pola obowiązkowego), kafel kontaktowy włączony.
- **[h5rf3g]** Listing branży („branża bieżącej strony"): produkty z tą branżą ([taksonomie.md](taksonomie.md), [82fpks]), w sekcjach drzewa oferty jak w menu — sekcja kategorii najwyższego poziomu (nagłówek H3 na ciemnej belce, karty przypięte bezpośrednio do niej), podsekcje podkategorii (H4 + siatka; produkt z głębszego poziomu — w podsekcji przodka drugiego poziomu); nagłówki bez linków; kolejność sekcji — kolejność termów, kart — kolejność listingu; sekcje bez produktów pominięte; produkty bez kategorii (i z termu spoza drzewa) — na końcu, w osobnej siatce bez nagłówka; produkt z kilkoma kategoriami — raz, wg pierwszego termu; listing bez produktów jest pusty.
- **[w774pg]** Nad sekcjami listingu branży — ogólny nagłówek bloku (H2). Kafel kontaktowy — ostatnia pozycja ostatniej siatki całego listingu (siatki produktów bez kategorii; gdy jej brak — ostatniej podsekcji ostatniej sekcji albo samej sekcji); w edytorze — przez portal. Tryb listingu branży włącza parametr `$branza` funkcji grupy.

## Strony filarów

- **[9vnuvd]** Strony filarów — cztery zwykłe strony (`page`), dzieci „O firmie" (adresy `/o-firmie/<slug>/`), do których linkują karty hero strony głównej; bez własnego wzorca, nowa strona filaru — od wzorca „Strona kontentowa" ([wzorce-stron.md](wzorce-stron.md), [hegdab]). Skład: Top visual kontentowy, Karty informacyjne, Kafle produktowe (blok na obszar filaru: wybór ręczny, bez kafla kontaktowego), Belka informacyjna odmiany 2, Proces współpracy, Kalendarium (w miejscu artykułów tematycznych), Sekcja kontaktowa.
