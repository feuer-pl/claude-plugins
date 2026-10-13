# Taksonomie

Taksonomie produktu: kategorie oferty (`oferta`), branże (`branza`), grupy produktów (`grupa`), oznaczenia (`oznaczenie`) — pola termów, kolejność, blokady. Produkt: [produkt.md](produkt.md); przegląd modelu: [model-tresci.md](model-tresci.md).

## Wspólne

- **[ae4keu]** Wszystkie cztery taksonomie są przypisane wyłącznie do typu `produkt`; artykuły i strony ich nie mają.
- **[98f2ex]** `branza`, `grupa` i `oznaczenie` są hierarchiczne wyłącznie po to, żeby edytor (panel produktu, szybka edycja listy produktów) pokazywał listę pól wyboru zamiast pola z podpowiedziami. Hierarchię uwzględnia tylko zapytanie Kafli produktowych po branży (domyślnie z produktami branż podrzędnych). W `branza` i `grupa` pole nadrzędne zostaje, z opisem „Bez wpływu na serwis — zostaw „Brak"." — rodzic daje tylko wcięcie na listach.
- **[rk76jt]** Etykiety w panelu: `branza` i `grupa` — komplet własnych etykiet (panel edytora, ekrany termów, komunikaty, pasek administracyjny; słowo „kategoria" nie pada w żadnej), bo dla taksonomii hierarchicznej WordPress podstawia etykiety kategorii; `grupa` bez `template_name` i bez odnośnika „Zobacz grupę" w pasku administracyjnym. `oferta` — etykiety kategorii z nazwami „Oferta" / „Kategoria oferty"; `oznaczenie` — tylko „Oznaczenia" / „Oznaczenie". Etykiety przez i18n (domena `feuer-komponenty`).
- **[743k7k]** `grupa` i `oznaczenie` są w REST mimo niepubliczności (korzysta z nich panel edytora produktu).
- **[52n8r5]** `oferta`, `branza` i `grupa` nie mają własnych uprawnień: termy dodaje, zmienia i usuwa każdy z `manage_categories` (m.in. redaktor), przypisuje do produktu każdy z `edit_posts`.
- **[jn6u63]** Termy `oferta`, `branza` i `grupa` zakłada, zmienia i usuwa się także z czatu, na tych samych uprawnieniach — operacje taksonomii (cms-z-czatu.md, „Operacje taksonomii"): slug termu zostaje, a usunąć da się wyłącznie term pusty — bez produktów i bez termów podrzędnych.
- **[h8w3gb]** Taksonomie wbudowane WordPressa (`category`, `post_tag`, `post_format`) nie są używane przez serwis; artykuły mają domyślną kategorię `uncategorized`.

### Pola termu `branza` i `oferta`

| ID | Pole | Klucz | Typ i wartości | Dozwolone | Wymagane / domyślne | Uwagi |
|---|---|---|---|---|---|---|
| **[sxgpfm]** | Ikona | `_feuer_ikona` | ID załącznika (liczba ≥ 0) | medium: obraz (także SVG) | 0 = brak | branża — ikona kafelka branży; kategoria — ikona kafla kategorii |
| **[nrgnra]** | Zdjęcie | `_feuer_zdjecie` | ID załącznika (liczba ≥ 0) | medium: obraz | 0 = brak | branża — zdjęcie w bloku „Branże" mega-panelu menu; kategoria — kafel kategorii i top visual strony kategorii |

- **[78ghuw]** Pola plików termu (Ikona, Zdjęcie) mają wyłącznie `branza` i `oferta`; meta termu w REST, zapis — uprawnienie z [52n8r5].
- **[y6guyt]** Formularz dodawania i edycji termu `branza` / `oferta`: pod polami WordPressa kolejno Ikona, Zdjęcie, Kolejność (tylko branża) i pola SEO ([seo.md](seo.md), [jsncvy]).
- **[bbk78s]** Pole pliku: „Wybierz: Ikona" / „Wybierz: Zdjęcie" otwiera bibliotekę mediów (tylko obrazy, jeden plik); podgląd — miniatura (rozmiar `thumbnail`, a gdy go brak — oryginał); „Usuń" ustawia 0 i czyści podgląd, plik zostaje w bibliotece.
- **[7rrvjb]** W panelu pola termu zapisują się wyłącznie z formularza termu (pole `feuer_term`, nonce i uprawnienie z [52n8r5]; inaczej zapis pominięty bez komunikatu) — szybka edycja listy termów ich nie zmienia, a utworzenie albo zmiana termu z kodu ich nie zapisuje; operacje taksonomii z czatu zapisują meta termu wprost (cms-z-czatu.md, [t25wry]). Pole nieobecne w żądaniu formularza zapisuje się jako 0 (pliki, kolejność) albo pusty tekst (SEO); czyszczenie — `sanitize_callback` meta termu, te same co w REST.
- **[bhw589]** Ikony branż i kategorii oferty pochodzą z zestawu Tabler Icons 3.48.0 (licencja MIT), pliki SVG w bibliotece mediów; kategoria „Compliance, audyty i doradztwo" ma ikonę własną.

## Oferta (`oferta`)

- **[d93cgu]** Hierarchia oferty to jedna hierarchiczna taksonomia `oferta` (termy rodzic–dziecko), nie hierarchia stron. Rejestrowana bez typów wpisów — podpina ją typ produktowy (`produkt`).
- **[66s4x2]** Kod nie ogranicza głębokości drzewa.
- **[xktvsv]** Kolejność kategorii oferty — wszędzie, gdzie serwis je wylicza (menu, stopka, drzewa, listy rodzeństwa, kafle kategorii, grupy Listy artykułów): kolejność utworzenia (ID termu), bez ręcznego sortowania.
- **[u9pkpc]** Publiczna: strona termu pod płaskim adresem `/oferta/<slug-termu>/`, niezależnie od pozycji w drzewie; w REST; kolumna „Oferta" na liście produktów.
- **[bsbyqn]** Produkt ma jeden term `oferta` (jedną ścieżkę w drzewie); kod tego nie wymusza i nie może blokować przejścia na wiele termów — przy wielu termach okruszki biorą pierwszy.
- **[tvgyua]** Nazwa, opis, zdjęcie i ikona kategorii żyją w termie; strony zbiorcze ich nie kopiują ([strony-zbiorcze.md](strony-zbiorcze.md), [47wr84], [n7rpch]).
- **[r9sy27]** Pod polem „Zdjęcie" kategorii podpowiedź „Zdjęcie poziome, ok. 16:9, min. 1920 px szerokości, główny motyw w środku kadru."; kadr przycina komponent.
- **[e34mdr]** Przy utworzeniu termu `oferta` powstaje sekcja kategorii ([sekcje.md](sekcje.md)).

## Branża (`branza`)

- **[82fpks]** Produkt każdego rodzaju ma dowolną liczbę branż, także żadną. Produkt bez branży dotyczy wszystkich branż: jest na każdej stronie branży i w źródle „branża" Kafli produktowych; Lista artykułów ze źródłem „branża" bierze wyłącznie artykuły produktów z tą branżą przypisaną wprost.
- **[wkeeu2]** Publiczna: strona branży pod `/branza/<slug-termu>/` (szablon „Strona branży"); w REST; kolumna „Branże" na liście produktów.
- **[2ue5f6]** Pole „Kolejność" (`_feuer_kolejnosc`) — pole liczbowe w formularzu termu (krok 1); zapis jako tekst (pusta wartość liczbowa w REST byłaby 0): liczba całkowita, ułamek obcięty, wartość nienumeryczna → pusty tekst; pusty = bez ręcznej kolejności. W REST.
- **[4c6qy5]** Lista branż: wszystkie termy (także bez produktów), rosnąco wg „Kolejność"; bez wartości — na końcu; przy równej wartości (także wśród pustych) alfabetycznie po nazwie. Błąd pobrania termów — pusta lista.
- **[wngjx8]** Ta sama lista i kolejność: blok „Branże" mega-panelu menu, kafelki branż na stronie głównej, okruszki strony branży, tagi branż na liście artykułów Bazy wiedzy.
- **[jw2d32]** Przy utworzeniu termu `branza` powstaje sekcja branży ([sekcje.md](sekcje.md)).

## Grupa produktów (`grupa`)

- **[3stw5s]** Niepubliczna: bez stron i adresów; zapytanie z frontu `?taxonomy=grupa` jest ignorowane.
- **[8cuu94]** Termy tworzy i redaguje redaktor w panelu (ekran termów w menu „Produkty"); produkt każdego rodzaju może mieć dowolną liczbę grup — wybór w natywnym panelu bocznym edytora produktu; kolumna „Grupy produktów" na liście produktów.
- **[2sg6dc]** Grupy nie są pokazywane na froncie przez żaden blok ani szablon.

## Oznaczenia (`oznaczenie`)

- **[ydgj9z]** Słownik zamknięty: „TOP 20" (`top-20`) i 12 miesięcy od „Styczeń" do „Grudzień" (slugi bez polskich znaków: `styczen` … `grudzien`). Słownik żyje w kodzie (`feuer_oznaczenia()`) — zmiana słownika = zmiana kodu.
- **[vt4rpq]** Kod traktuje każde oznaczenie poza `top-20` jako miesiąc (numer = pozycja w słowniku po „TOP 20"; `feuer_najblizszy_miesiac()`): Kalendarium, panele „Miesiące" (Kafle produktowe, Lista artykułów) i najbliższy miesiąc kart TOP 20. Oznaczenie niebędące miesiącem wymaga zmiany tych miejsc w kodzie.
- **[z3qwb4]** Produkt może mieć dowolną liczbę oznaczeń; produkt sezonowy = produkt z co najmniej jednym miesiącem, zakres miesięcy = kilka zaznaczeń.
- **[rx84hh]** Termów nie da się dodać, zmienić ani usunąć — w panelu, w REST i z czatu, także administratorowi (`manage_terms`, `edit_terms`, `delete_terms` = `do_not_allow`; ekranu termów nie ma w menu); przypisywanie — uprawnienie `edit_posts`. Redaktor tylko zaznacza.
- **[8mfe59]** Termy tworzy kod (`feuer_oznaczenia_termy()` na `init`): brakujące dodaje, nazwy istniejących wyrównuje do słownika — wyłącznie po zmianie słownika (skrót md5 słownika w opcji `feuer_oznaczenia`), na nowym środowisku przy pierwszym żądaniu. Skrót zapisuje się tylko, gdy żadna operacja na termach nie zwróciła błędu — inaczej synchronizacja powtarza się przy kolejnych żądaniach.
- **[t4ea7p]** Term usunięty ze słownika nie jest kasowany przez kod (straciłby przypisania produktów) — usuwa się go ręcznie, WP-CLI. Term usunięty ręcznie nie wraca, dopóki słownik się nie zmieni albo opcja `feuer_oznaczenia` nie zostanie usunięta.
- **[8mugy9]** Niepubliczna: bez stron i adresów (`/oznaczenie/<slug>/` — 404); zapytania z frontu (`?oznaczenie=…`, `?taxonomy=oznaczenie&term=…`) są ignorowane — zmienna zapytania działa tylko w panelu. Odbiorcy wybierają produkty zapytaniem po taksonomii po stronie serwera (`tax_query` po slugu).
- **[fs8d5p]** Kolejność zawsze wg słownika (TOP 20, potem miesiące od stycznia), nie alfabetycznie: panel edytora, kolumna i filtr listy produktów, szybka edycja. Zapytania o termy oznaczeń zwracają wyłącznie termy ze słownika; term spoza słownika przypisany produktowi — na końcu. „TOP 20" nie ma własnej kolejności produktów.
- **[sa7hx9]** Panel „Oznaczenia" w edytorze produktu — własna lista pól wyboru zamiast natywnej (pozostałe taksonomie — panele natywne): kolejność słownika (zaznaczone nie idą na górę), wygląd natywnego panelu, wskaźnik ładowania do wczytania listy, bez dodawania termów. „Szukaj oznaczeń" filtruje po fragmencie nazwy bez względu na wielkość liter i znaki diakrytyczne („pazdz" → Październik). Zaznaczenie zmienia oznaczenia wpisu, zapisywane z wpisem.
- **[cjbpn8]** W szybkiej edycji listy produktów — natywna lista pól wyboru; termy bez rodzica.
- **[psav3n]** Lista produktów w panelu: kolumna „Oznaczenia" (kliknięcie oznaczenia filtruje listę) i lista „Wszystkie oznaczenia" obok „Wszystkie daty" (wybór jednego oznaczenia, kolejność słownika) — działa tylko w panelu.
- **[5mwwjx]** Oznaczenia: zakres tłumaczeń i synchronizacja — [wielojezycznosc.md](wielojezycznosc.md), [7n3mcs], [jrtygf]; redaktor zaznacza je raz.
- **[6pqtnx]** Odbiorcy: źródła „TOP 20" i „Miesiące" bloków z listą pozycji ([bloki.md](bloki.md), [fn4snx]; źródła — README bloków).
