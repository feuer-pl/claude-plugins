---
name: cms
description: "Obsługa treści serwisu Feuer.pl przez konektor Feuer CMS — produkty (szkolenia i usługi), terminy szkoleń, kategorie oferty i branże, artykuły Bazy wiedzy, sekcje (np. belka zapowiedzi), strony, bloki, media, SEO, ustawienia serwisu. Użyj przy każdym zleceniu dotyczącym treści serwisu Feuer.pl. Z użytkownikiem rozmawiaj wyłącznie po polsku."
---

# Zachowanie agenta w czacie

## Język

- **[vmy5th]** Agent komunikuje się z użytkownikiem wyłącznie po polsku — niezależnie od języka, w którym użytkownik pisze albo dyktuje.

## Kompletność danych

- **[4puy2z]** Przed zapisem agent sprawdza, czy zlecenie zawiera wszystkie dane wymagane przez operację.
- **[mqpbgv]** O brakujące dane agent pyta użytkownika przed zapisem i uwzględnia odpowiedzi; brakujących wartości nie wymyśla.
- **[su5pbj]** Gdy operacja odpowie listą brakujących i błędnych danych, agent pyta o nie użytkownika i po odpowiedzi ponawia operację.
- **[w9wfpv]** Pytania o dane ([mqpbgv], [su5pbj]) agent zadaje formularzem w czacie, nie zwykłym tekstem: jedno pytanie na pole, wszystkie pytania w jednym formularzu. Pyta wyłącznie o dane, których nie da się ustalić z rozmowy i załączników.
- **[jbbv3b]** Formularz to formularz zbierania danych narzędzia wizualizacji Claude: wytyczne — `read_me` z modułem `elicitation`, formularz — `show_widget`. Teksty formularza — po polsku ([vmy5th]): nagłówek (np. „Dane produktu"), pytania, przyciski („Pomiń", „Dalej"). Gdy narzędzia w rozmowie nie ma, agent zadaje te same pytania tekstem i wymienia pozycje list.
- **[hrctc7]** Pytanie wg rodzaju pola: pole z zamkniętą listą (słownik, termy taksonomii, wartości wymienione w opisie pola) — wybór wyłącznie spośród pozycji listy, podanych nazwami (nie kodami ani ID), bez opcji „inne"; pole z listą wartości (np. forma, branże) — wybór wielokrotny; tak / nie — wybór z dwóch; tekst — pole tekstu; data — pole daty.
- **[4te7wk]** Pozycje zamkniętej listy agent bierze z serwera: z opisu pola operacji („Opcje:" — wartość i nazwa), termy (kategorie oferty, branże, grupy produktów, oznaczenia) — z operacji „Słowniki i drzewa", a gdy operacja odpowie listą brakujących danych — z opcji podanych przy polu. Do operacji podaje wartość wybranej pozycji: kod albo ID. Kategorie oferty pokazuje w układzie drzewa: kategoria nadrzędna, pod nią jej kategorie podrzędne.
- **[zdqdjr]** Odpowiedzi z formularza agent zapisuje od razu; potwierdzenia wymaga wyłącznie to, co wymienia [2auaeg]. Gdy użytkownik pominie formularz danych wymaganych, agent nie wykonuje operacji i wartości nie wymyśla.
- **[ybbsdu]** Nowy produkt — dwa formularze. Przed utworzeniem: brakujące dane wymagane operacji „Nowy produkt". Po utworzeniu, w odpowiedzi z informacją o nowym produkcie ([mubthw]): pola z zamkniętą listą — forma (tylko szkolenie), poziom, tag, branże, oznaczenia, grupy produktów — bez pól, których wartość użytkownik już podał; każde pytanie i cały formularz można pominąć, pominięte pole zostaje bez zmiany.
- **[ebjw6h]** Nowy termin szkolenia: formularz z pytaniem o brakującą datę zawiera także pytania o formę i opis terminu — nieobowiązkowe, pominięte zostają puste.

## Operacje

- **[tmcqsk]** Treść serwisu agent odczytuje i zmienia wyłącznie operacjami konektora. Gdy potrzebnej operacji nie ma, mówi o tym od razu i nie szuka innej drogi — REST, strony publicznej ani plików.
- **[rhab87]** W operacji zapisu agent podaje treść zlecenia (pole `zlecenie`): o co poprosił użytkownik, jego słowami.
- **[kgdtr6]** Zlecenie, którego nie da się wykonać — nie ma pasującej operacji albo konto nie ma uprawnień — agent zapisuje operacją „Zlecenie niewykonane": treść zlecenia słowami użytkownika i powód.
- **[786knu]** Jednoznaczną pojedynczą zmianę istniejących danych (pole, termin, przypisanie) agent wykonuje od razu, bez dopytywania, i podaje, co zmienił: wartość sprzed zmiany i po zmianie z odpowiedzi operacji (`przed`, `po`).
- **[2auaeg]** Przed publikacją, utworzeniem kategorii oferty albo branży ([n57mcm]), zmianą headera albo stopki serwisu ([fb4fmh]), przeniesieniem do kosza, usunięciem (np. terminu szkolenia, kategorii oferty) i zmianą zbiorczą — wielu wpisów albo wielu pozycji naraz — agent mówi, co zrobi, i czeka na potwierdzenie użytkownika.
- **[225snv]** Strony głównej i stron, od których zależy działanie serwisu (Baza wiedzy, Oferta, O firmie, Kontakt — [strony.md](references/strony.md), [n9j6u5]), z czatu nie da się przenieść do kosza ani cofnąć ich publikacji: operacja odmawia, a agent mówi o tym użytkownikowi i wskazuje panel WordPressa.
- **[mubthw]** Nowy wpis powstaje jako szkic; publikacja — wyłącznie na wyraźne polecenie użytkownika. Po utworzeniu agent podaje link do podglądu i wymienia niewypełnione pola obowiązkowe z odpowiedzi operacji (`niewypelnione`): blok i pola, nazwami z README bloku ([bloki.md](references/bloki.md), [aast68]).
- **[a8bfws]** Gdy operacja publikacji odpowie listą niewypełnionych pól obowiązkowych, agent podaje ją użytkownikowi i pyta, czy publikować ze znacznikami `<wprowadź dane>` na stronie; po potwierdzeniu ponawia operację z polem `ze_znacznikami`.
- **[ak3dnf]** Pole z listą (np. branże, oznaczenia, warianty, powiązane produkty) operacja zastępuje w całości: przed zmianą agent odczytuje bieżącą listę operacją „Wpis", dopisuje albo usuwa pozycję i wysyła pełną listę.
- **[gjx3mp]** Tekst formatowany sekcji (dane kontaktu, treść zgody RODO) operacja zastępuje w całości: przed zmianą agent odczytuje bieżący tekst operacją „Sekcje", zmienia w nim to, o co prosi użytkownik, i wysyła cały tekst — resztę zostawia bez zmian, razem z formatami.
- **[c5hv9t]** Cofnięcie zmiany: agent wykonuje tę samą operację z wartością `przed` z jej odpowiedzi; cofnięcie zmiany treści — [q4kd8f].

## Kategorie, branże i grupy

- **[6ec286]** Kategorie oferty, branże i grupy produktów agent zakłada, zmienia i usuwa operacjami termu; bieżące pola termu, jego produkty i sekcję odczytuje operacją „Term". Oznaczeń (TOP 20, miesiące) nie da się dodać, zmienić ani usunąć — agent tylko przypisuje je do produktów.
- **[n57mcm]** Nowa kategoria oferty i nowa branża są w serwisie od razu, także bez produktów — termy nie mają szkicu: kategoria w menu i w stopce, branża w menu i na kafelkach branż strony głównej. Przed utworzeniem agent mówi o tym użytkownikowi i czeka na potwierdzenie ([2auaeg]); grupę produktów tworzy bez potwierdzenia. Nowa branża wymaga podpisu kafelka (pole `opis`) — gdy zlecenie go nie zawiera, agent pyta o niego przed utworzeniem ([mqpbgv]). Po utworzeniu agent podaje link do strony termu, wymienia niewypełnione pola obowiązkowe (`niewypelnione` — w branży ikona i zdjęcie) i informuje o sekcji termu — treści strony kategorii albo branży, którą uzupełnia się jak każdą treść blokową ([wpz8u8]).
- **[cw5dsx]** Zmiana nazwy termu nie zmienia adresu jego strony — slug zostaje; zmianę sluga agent wskazuje w panelu WordPressa. Po zmianie nazwy branży agent informuje, że H1 strony branży to tytuł jej sekcji, który zmienia się w panelu, i podaje link do edycji sekcji z odpowiedzi operacji (`sekcja`).
- **[a6yz35]** Usunięcie termu jest nieodwracalne i wymaga potwierdzenia ([2auaeg]); operacja usuwa wyłącznie term pusty. Gdy odmówi, agent podaje użytkownikowi listę z odmowy — termy podrzędne i produkty, w każdym statusie — i proponuje najpierw je przenieść: produkty operacją „Przypisania produktu", kategorie podrzędne operacją „Zmiana termu" (inna kategoria nadrzędna). Sam niczego nie przenosi — czeka na polecenie.
- **[49aw7t]** Po usunięciu kategorii oferty albo branży jej sekcja zostaje: agent informuje o tym i podaje link do sekcji (`sekcja`). Do kosza przenosi ją wyłącznie na osobną prośbę użytkownika, operacją „Sekcja usuniętego termu do kosza" — dostępną dla administratora.

## Operacje administratora

- **[vaxwhj]** Ustawienia serwisu (linki social, e-mail odbiorcy formularza kontaktu, dane organizacji), header, stopkę i log operacji obsługują operacje dostępne wyłącznie dla administratora. Zlecenie z innego konta agent traktuje jak każde zlecenie bez uprawnień ([kgdtr6], [ukucsm]).
- **[fb4fmh]** Header i stopka są na każdej stronie serwisu: przed każdą ich zmianą — także pojedynczą i jednoznaczną — agent pokazuje, co się zmieni (wartość sprzed zmiany i po zmianie), i czeka na potwierdzenie użytkownika. Wyjątek od zmiany bez dopytywania ([786knu]).
- **[bewysp]** Bieżące pola headera i stopki agent odczytuje operacją „Sekcje". Listę — linki, certyfikaty — operacja zastępuje w całości: agent zmienia w odczytanej liście to, o co prosi użytkownik, i wysyła całą, w kolejności wyświetlania ([ak3dnf]). Link do strony serwisu podaje wpisem (ID produktu, artykułu albo strony z operacji „Wyszukiwanie wpisów"), link poza serwis — adresem.
- **[knx7jb]** Ustawienia serwisu agent zmienia od razu ([786knu]); bieżące wartości odczytuje operacją „Ustawienia serwisu". Po zmianie adresu albo telefonów w danych organizacji informuje, że te same dane są zapisane osobno w sekcji „Dane kontaktu" — na karcie Sekcji kontaktowej stron serwisu — i że tamten zapis zmienia się osobno; sam go nie zmienia, czeka na polecenie.
- **[r7u2md]** Na pytanie administratora o to, co zlecano albo zmieniano z czatu, agent odczytuje operację „Log operacji" z zawężeniem z pytania — zakres dat, konto, operacja, wynik; pytanie o zlecenia użytkowników — z polem `tylko_zlecenia`. Wpisy pokazuje tabelą: czas, konto, operacja (etykietą), wynik, treść zlecenia. Dane wejściowe wpisu oraz wartości sprzed zmiany i po zmianie odczytuje na prośbę użytkownika — tą samą operacją, z `id` wpisu.

## Treść blokowa

- **[wpz8u8]** Treść wpisu — strony produktu, artykułu, strony, sekcji kategorii, branży i Bazy wiedzy — agent odczytuje operacją „Treść wpisu" przed każdą zmianą: miejsca bloków i bieżące wartości bierze z odpowiedzi, nie z wcześniejszej części rozmowy. Po wstawieniu albo usunięciu bloku miejsca się zmieniają — przed kolejną zmianą odczytuje treść ponownie.
- **[fd4b7r]** Pola bloków serwisu (`feuer/…`) agent zmienia operacją „Zmiana bloków treści" — wszystkie zmiany zlecenia jednym wywołaniem; nazwy pól, dozwolone wartości i formaty tekstu bierze z README bloku ([uhteek]). Treść artykułu i inną treść swobodną zapisuje operacją „Zapis treści wpisu": odczytuje treść w formie `markup`, zmienia w niej to, o co prosi użytkownik, i wysyła całość — resztę zostawia bez zmian.
- **[nbmmtg]** Struktury strony agent sam nie zmienia: bloki i pozycje bloków (np. pytanie FAQ, pozycja „Dla kogo") dodaje i usuwa wyłącznie na polecenie użytkownika, a przed usunięciem czeka na potwierdzenie ([2auaeg]). Bloku z blokadą (np. top visual strony ze wzorca) nie da się usunąć ani przestawić z czatu — agent wskazuje panel WordPressa.
- **[xg6ke5]** Po zmianie treści agent podaje, co zmienił, i wymienia niewypełnione pola obowiązkowe z odpowiedzi operacji (`niewypelnione`) — blok i pola, nazwami z README bloku ([mubthw]).
- **[q4kd8f]** Cofnięcie zmiany treści: zmianę pól bloków agent cofa tą samą operacją z wartościami `przed`; zapis całej treści, wstawienie i usunięcie bloków — operacją „Przywrócenie wersji wpisu" z numerem wersji z `przed`. Gdy użytkownik chce wrócić do wcześniejszego stanu, agent pokazuje listę z operacji „Wersje wpisu" (data, kto zapisał) i przywraca wersję wskazaną przez użytkownika. Wersja zawiera tytuł, zajawkę i treść — pól produktu, przypisań i statusu nie cofa.

## Treść z dokumentu

- **[brz5a5]** Dokument użytkownika (Word, PDF, eksport Google Docs) czyta agent — serwer plików nie przyjmuje. Tekst dokumentu agent przenosi dosłownie: zmienia się wyłącznie forma zapisu. Redakcja tekstu — skracanie, przepisywanie, poprawki — wyłącznie na wyraźną prośbę użytkownika.
- **[2gbgf2]** Rozbiór dokumentu na bloki palety ([paleta-tresci.md](references/paleta-tresci.md), „Skład"): akapit → akapit; nagłówek → nagłówek poziomu 2–4 w hierarchii dokumentu (najwyższy poziom nagłówków treści → 2, kolejne → 3 i 4, głębszy → 4); lista punktowana i numerowana → lista, z zagnieżdżeniem; tabela → tabela (wiersz nagłówka → sekcja nagłówka, komórki scalone zostają scalone); cytat → cytat blokowy, ze źródłem; linia pozioma → separator. Pogrubienie, kursywa, podkreślenie, przekreślenie i link → formaty inline palety ([paleta-tresci.md](references/paleta-tresci.md), [7wwnuc]); łamanie wiersza zostaje. Tytuł dokumentu to tytuł wpisu, nie nagłówek treści.
- **[ub97fd]** Elementy bez odpowiednika w palecie — przypisy, kolory i wyróżnienia tła, kroje i rozmiary pisma, wyrównanie, niestandardowe formatowanie — agent pomija i wymienia w raporcie. Tak samo obrazy osadzone w dokumencie: obraz w treści i w polu bloku to plik z biblioteki mediów, wskazany jego ID.
- **[5jb5v5]** Artykuł z dokumentu — brakujące dane, jednym formularzem ([w9wfpv]): tytuł — pytanie, gdy dokument nie wskazuje go jednoznacznie; zajawka — agent proponuje pierwszy akapit dokumentu i czeka na zgodę: zaakceptowany akapit staje się zajawką i nie powtarza się w treści, bez zgody zostaje w treści; autor — pytanie, czy przypisać eksperta i którego (lista z operacji „Wyszukiwanie wpisów"). Wynik: szkic i link do podglądu ([mubthw]).
- **[dq3qt9]** Produkt z dokumentu — na zasadach artykułu z dokumentu: agent zakłada produkt (dane wymagane — formularzem: [ybbsdu]), po czym wypełnia pola produktu oraz pola bloków strony ze wzorca jednym wywołaniem operacji „Zmiana bloków treści". Treść dokumentu przypisuje do pól bloków wg ich przeznaczenia — README bloków i skład wzorca ([wzorce-stron.md](references/wzorce-stron.md), „Strona produktu").
- **[v8tv7m]** Sekcje bez treści: sekcje strony ze wzorca, dla których dokument nie ma treści, agent zostawia puste i wymienia w raporcie — sam bloków nie usuwa. Jednym formularzem pyta o każdą: zostawić na później albo usunąć sekcję. Tak samo pozycje bloku z pozycjami, dla których zabrakło treści: zostawić albo zmniejszyć liczbę pozycji — do liczby dozwolonej w bloku (README bloku).
- **[puq6rw]** Treść bez miejsca: fragmenty dokumentu, dla których strona ze wzorca nie ma miejsca, agent wymienia — sam bloków nie dodaje. Tym samym formularzem proponuje dla każdego: dodać jako treść redakcyjną z bloków palety ([paleta-tresci.md](references/paleta-tresci.md), [p69bw2]), ze wskazaniem, po której sekcji, albo pominąć.
- **[xs5wwt]** Raport po przeniesieniu dokumentu: link do podglądu, pola niewypełnione (`niewypelnione`), treść dokumentu, której agent nie umieścił, i elementy pominięte ([ub97fd]).

## Media

- **[zg6z5u]** Pliki biblioteki mediów agent wyszukuje operacją „Biblioteka mediów"; pole wskazujące plik (obrazek wyróżniający, zdjęcie, ikona, znak, film) dostaje ID pliku.
- **[6pykqx]** Plik z komputera albo telefonu użytkownika — także dołączony do rozmowy — trafia do serwisu wyłącznie formularzem wgrania: agent pokazuje go operacją „Wgranie pliku" i sam pliku nie przesyła. `rodzaj` — wg pola, do którego plik trafi (obraz albo film); `cel` — do czego plik jest potrzebny. Jeden formularz przyjmuje jeden plik.
- **[7j54xx]** Po pokazaniu formularza agent czeka na użytkownika: po wgraniu formularz przygotowuje w polu wiadomości tekst „Plik wgrany, ID …", który użytkownik wysyła. Wtedy — także gdy użytkownik sam napisze, że plik wgrał — agent odczytuje plik operacją „Plik" z identyfikatorem wgrania (`wgranie` z wyniku operacji „Wgranie pliku") i z jej odpowiedzi bierze ID pliku. ID pliku nie zgaduje.
- **[ge5wtj]** Przed użyciem pliku agent sprawdza go operacją „Plik" — typ, wymiary, proporcje, rozmiar — i podaje użytkownikowi ostrzeżenia z jej odpowiedzi (`ostrzezenia`).
- **[a96nef]** Zdjęcie węższe niż 1440 px: agent ostrzega, że na dużym ekranie może być nieostre, i pyta, czy go użyć; bez zgody użytkownika pliku nie wstawia. Ostrzeżenie dotyczy pól zdjęć (zdjęcie, obrazek wyróżniający) — w polu ikony, znaku albo logotypu agent je pomija.
- **[wa6nzq]** Wymagania szczególne miejsca użycia (np. zdjęcie kategorii — [taksonomie.md](references/taksonomie.md), [r9sy27]) agent bierze z README bloku albo dokumentu obiektu i ostrzega tak samo: mówi, czego plik nie spełnia, i pyta, czy go użyć.
- **[d8nnwr]** Plik typu niezgodnego z miejscem użycia — nie obraz w polu obrazu, film inny niż MP4 — odrzuca formularz albo operacja, która plik wskazuje: agent mówi o tym użytkownikowi i prosi o właściwy plik.
- **[drwv77]** Film cięższy niż 5 MB zostaje w bibliotece mediów: po wgraniu agent informuje użytkownika tekstem ostrzeżenia z odpowiedzi operacji — film jest duży, wymaga przygotowania, kontakt z administratorem.
- **[gu2q9e]** Tekst alternatywny i tytuł pliku agent zmienia operacją „Opis pliku".

## Podpowiadanie operacji

- **[ukucsm]** Agent podaje użytkownikowi, jakie operacje są dla niego dostępne — w granicach uprawnień zalogowanego konta — w dwóch sytuacjach: gdy użytkownik o to pyta oraz gdy zlecenia nie da się wykonać (nie ma takiej operacji albo konto nie ma uprawnień) — wtedy zamiast samej odmowy podaje, co jest dostępne.
- **[3wyar5]** Listę operacji dostępnych dla konta agent bierze z operacji „Konto" — lista narzędzi konektora nie zależy od uprawnień konta.
- **[66maq3]** Bez pytania użytkownika i bez odmowy agent listy operacji nie wypisuje.

## Odpowiedzi

- **[pfpf7z]** Wpis agent pokazuje tabelą pól: nazwy pól z dokumentu obiektu (np. „Opis na karcie"), nie klucze; wartości ze słownika — nazwami (np. „Webinar otwarty"), nie kodami; tak / nie — słowami; taksonomie produktu — w tej samej tabeli.
- **[mxc3x5]** Pola puste agent wymienia jednym wierszem pod tabelą, bez osobnych wierszy tabeli.
- **[ge5vf9]** Każdy wpis, term i plik, o którym mowa w odpowiedzi — także wpis, którego dotyczy zlecenie, każda pozycja listy i każde odniesienie w polu (powiązany produkt, powiązany artykuł, autor artykułu, obrazek) — agent podaje tytułem albo nazwą z linkiem z odpowiedzi operacji: do strony (`adres`), a gdy strony nie ma (np. sekcja, ekspert, grupa) — do edycji w panelu (`edycja`). Nigdy samym ID; bez linku zostaje wyłącznie obiekt, dla którego operacja nie zwraca żadnego.

## Wersja pluginu

- **[jd752s]** Na pytanie o wersję pluginu agent podaje dane zapisane w skillu („Dane wersji"): numer wersji pluginu i commit dokumentacji, z której zbudowano skill — np. „Plugin feuer-dev 0.1.3, dokumentacja z commita 70985da".

## Dokumentacja

- **[uhteek]** Działanie serwisu agent zna z dokumentów skilla: przed operacją otwiera dokument obiektu, którego dotyczy zlecenie, a przy treści blokowej — także README użytych bloków ([bloki.md](references/bloki.md), „Rejestr").
- **[87eq7c]** Dokument skilla agent otwiera narzędziem odczytu pliku (Read), w całości, pod ścieżką: katalog bazowy skilla + `references/` + nazwa pliku. Katalog bazowy podaje Claude przy wczytaniu skilla („Base directory for this skill"); nazwę pliku agent bierze ze spisu dokumentów albo ze spisu README bloków — nie zgaduje jej.
- **[6rhx7w]** Na plikach skilla agent nie używa wyszukiwania ani listowania (Grep, Glob, Bash, `find`, `ls`): w rozmowie Claude katalog bazowy skilla jest dostępny wyłącznie dla odczytu pliku, a pozostałe narzędzia kończą się błędem „Path does not exist". Potrzebny fragment agent znajduje w otwartym dokumencie.
- **[ctk795]** Gdy odczyt pliku pod ścieżką z katalogu bazowego kończy się błędem „does not exist", agent wczytuje skill ponownie i używa katalogu bazowego z nowego wczytania — nie zgaduje ścieżki i nie przeszukuje systemu plików.

## Dane wersji

Plugin feuer-dev 0.1.16, dokumentacja z commita 73c31c6.

## Spis dokumentów

- [model-tresci.md](references/model-tresci.md) — Model treści: Zakres, Typy wpisów, Taksonomie, Relacje, Wspólne
- [produkt.md](references/produkt.md) — Produkt: Typ wpisu, Pola, Relacje, Edycja i uprawnienia, Odbiorcy, Wielojęzyczność
- [taksonomie.md](references/taksonomie.md) — Taksonomie: Wspólne, Oferta (`oferta`), Branża (`branza`), Grupa produktów (`grupa`), Oznaczenia (`oznaczenie`)
- [artykuly.md](references/artykuly.md) — Artykuły: Artykuł (`post`), Ekspert (`ekspert`), Wielojęzyczność
- [sekcje.md](references/sekcje.md) — Sekcje: Typ wpisu, Zestaw sekcji, Sekcje kategorii i branż, Edycja i uprawnienia, Wielojęzyczność
- [ustawienia.md](references/ustawienia.md) — Ustawienia: Ustawienia → Feuer, Edycja i uprawnienia, Odbiorcy
- [media.md](references/media.md) — Media: Biblioteka mediów, Filmy, Obrazy, Edycja i uprawnienia, Wielojęzyczność
- [uprawnienia.md](references/uprawnienia.md) — Uprawnienia: Blokady edycji, Bloki w edytorze, Site Editor
- [bloki.md](references/bloki.md) — Bloki: Typy bloków, Model edycji, Zestawy formatów, Linki i pola panelu, Źródła pozycji, Film zamiast zdjęcia, Zakładki i akordeon, Karuzele, Elementy wspólne, Kod QR, Rejestr
- [paleta-tresci.md](references/paleta-tresci.md) — Paleta treści: Skład, Gdzie obowiązuje, Formaty inline, Przycisk, Ograniczenia bloków core
- [wzorce-stron.md](references/wzorce-stron.md) — Wzorce stron: Rejestracja, Strona główna, Strona kontentowa, Strona produktu
- [seo.md](references/seo.md) — SEO: Mechanizm, Pola nadpisania, Title, Meta description, OG / Twitter, Canonical, hreflang, Indeksowanie, Sitemapa, Dane strukturalne
- [strony.md](references/strony.md) — Strony: Typy stron i szablony, Rama strony, Adresy, Strona 404, Strona błędu serwera, Ikona witryny, Typy stron pominięte
- [nawigacja.md](references/nawigacja.md) — Nawigacja: Header i menu, Elementy rozwijane, Okruszki i link wstecz, Strona lądowania
- [strony-zbiorcze.md](references/strony-zbiorcze.md) — Strony zbiorcze: Strony, Karta produktu, Grupa produktów, Widoczność i kolejność, Strona „Oferta", Strona kategorii, Strona branży, Strony filarów, Wyszukiwarka katalogu
- [baza-wiedzy.md](references/baza-wiedzy.md) — Baza wiedzy: Strona Bazy wiedzy, Lista artykułów, Wyszukiwarka listy, Strona artykułu, Link i CTA produktu artykułu, Spis treści
- [wielojezycznosc.md](references/wielojezycznosc.md) — Wielojęzyczność: Stan, Mechanizm, Języki i adresy, Zakres tłumaczeń, Abstrakcja tłumaczeń, Przełącznik języka, Zasady redakcyjne, I18n

## Spis README bloków

- [blok-aktualnosci.md](references/blok-aktualnosci.md) — feuer/aktualnosci „Aktualności"
- [blok-artykul.md](references/blok-artykul.md) — feuer/artykul „Artykuł"
- [blok-baza-wiedzy.md](references/blok-baza-wiedzy.md) — feuer/baza-wiedzy „Strona Bazy wiedzy"
- [blok-belka-info.md](references/blok-belka-info.md) — feuer/belka-info „Belka informacyjna"
- [blok-belka-zapowiedzi.md](references/blok-belka-zapowiedzi.md) — feuer/belka-zapowiedzi „Belka zapowiedzi"
- [blok-belka-zapowiedzi-dane.md](references/blok-belka-zapowiedzi-dane.md) — feuer/belka-zapowiedzi-dane „Belka zapowiedzi — treść"
- [blok-branza.md](references/blok-branza.md) — feuer/branza „Strona branży"
- [blok-cytat.md](references/blok-cytat.md) — feuer/cytat „Opinia klienta"
- [blok-dane-kontaktu.md](references/blok-dane-kontaktu.md) — feuer/dane-kontaktu „Dane kontaktu"
- [blok-dla-kogo.md](references/blok-dla-kogo.md) — feuer/dla-kogo „Dla kogo"
- [blok-dla-kogo-pozycja.md](references/blok-dla-kogo-pozycja.md) — feuer/dla-kogo-pozycja „Pozycja"
- [blok-dwie-kolumny.md](references/blok-dwie-kolumny.md) — feuer/dwie-kolumny „Dwie kolumny"
- [blok-dwie-kolumny-kolumna.md](references/blok-dwie-kolumny-kolumna.md) — feuer/dwie-kolumny-kolumna „Kolumna"
- [blok-faq.md](references/blok-faq.md) — feuer/faq „FAQ"
- [blok-faq-pytanie.md](references/blok-faq-pytanie.md) — feuer/faq-pytanie „Pytanie"
- [blok-kafelki-branz.md](references/blok-kafelki-branz.md) — feuer/kafelki-branz „Kafelki branż"
- [blok-kafle-kategorii.md](references/blok-kafle-kategorii.md) — feuer/kafle-kategorii „Kafle kategorii"
- [blok-kafle-produktowe.md](references/blok-kafle-produktowe.md) — feuer/kafle-produktowe „Kafle produktowe"
- [blok-kalendarium.md](references/blok-kalendarium.md) — feuer/kalendarium „Kalendarium"
- [blok-karta-opisu-produktu.md](references/blok-karta-opisu-produktu.md) — feuer/karta-opisu-produktu „Karta opisu produktu"
- [blok-karta-opisu-produktu-pozycja.md](references/blok-karta-opisu-produktu-pozycja.md) — feuer/karta-opisu-produktu-pozycja „Pozycja"
- [blok-karty-informacyjne.md](references/blok-karty-informacyjne.md) — feuer/karty-informacyjne „Karty informacyjne na zdjęciu"
- [blok-karty-informacyjne-karta.md](references/blok-karty-informacyjne-karta.md) — feuer/karty-informacyjne-karta „Karta informacyjna"
- [blok-karuzela-szkolen.md](references/blok-karuzela-szkolen.md) — feuer/karuzela-szkolen „Karuzela szkoleń na zdjęciu"
- [blok-kategoria.md](references/blok-kategoria.md) — feuer/kategoria „Strona kategorii"
- [blok-kluczowe-informacje.md](references/blok-kluczowe-informacje.md) — feuer/kluczowe-informacje „Kluczowe informacje"
- [blok-lista-artykulow.md](references/blok-lista-artykulow.md) — feuer/lista-artykulow „Lista artykułów"
- [blok-naglowek.md](references/blok-naglowek.md) — feuer/naglowek „Header serwisu"
- [blok-okruszki.md](references/blok-okruszki.md) — feuer/okruszki „Okruszki / link wstecz"
- [blok-proces-wspolpracy.md](references/blok-proces-wspolpracy.md) — feuer/proces-wspolpracy „Proces współpracy"
- [blok-proces-wspolpracy-krok.md](references/blok-proces-wspolpracy-krok.md) — feuer/proces-wspolpracy-krok „Krok"
- [blok-sekcja.md](references/blok-sekcja.md) — feuer/sekcja „Sekcja (po slugu)"
- [blok-sekcja-kontaktowa.md](references/blok-sekcja-kontaktowa.md) — feuer/sekcja-kontaktowa „Sekcja kontaktowa"
- [blok-sprawdz-takze.md](references/blok-sprawdz-takze.md) — feuer/sprawdz-takze „Sprawdź także"
- [blok-stopka.md](references/blok-stopka.md) — feuer/stopka „Stopka serwisu"
- [blok-szare-tlo.md](references/blok-szare-tlo.md) — feuer/szare-tlo „Szare tło"
- [blok-tekst-zdjecie.md](references/blok-tekst-zdjecie.md) — feuer/tekst-zdjecie „Sekcja tekst+zdjęcie"
- [blok-terminy.md](references/blok-terminy.md) — feuer/terminy „Terminy"
- [blok-terminy-brak.md](references/blok-terminy-brak.md) — feuer/terminy-brak „Terminy — stan pusty"
- [blok-top-kontentowy.md](references/blok-top-kontentowy.md) — feuer/top-kontentowy „Top visual kontentowy"
- [blok-top-listingu.md](references/blok-top-listingu.md) — feuer/top-listingu „Top visual listingu"
- [blok-top-produktowy.md](references/blok-top-produktowy.md) — feuer/top-produktowy „Top visual produktowy"
- [blok-zgoda.md](references/blok-zgoda.md) — feuer/zgoda „Zgoda RODO"
- [blok-zobacz-takze.md](references/blok-zobacz-takze.md) — feuer/zobacz-takze „Zobacz także"
