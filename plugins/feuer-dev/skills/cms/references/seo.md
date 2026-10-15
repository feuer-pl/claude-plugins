# SEO

Metadane stron dla wyszukiwarek i podglądów linków (title, meta description, OG / Twitter, canonical, hreflang), indeksowanie, sitemapa, dane strukturalne, plik `/llms.txt` i wersje Markdown stron dla modeli językowych. Wymagania Google i pomiary: pomiary.md; ustawienia, z których korzystają metadane: [ustawienia.md](ustawienia.md); wersje językowe: [wielojezycznosc.md](wielojezycznosc.md).

## Mechanizm

- **[tkn3fk]** Metadane stron (title, meta description, OG / Twitter, canonical, sitemapa) generuje własny kod wtyczki `feuer-komponenty` (`includes/seo.php`), bez wtyczki SEO; dane strukturalne — `includes/dane-strukturalne.php` i render bloku FAQ.
- **[ek7qtj]** Meta description, OG / Twitter, canonical i pola nadpisania działają na stronach pojedynczych (artykuł, strona, produkt), stronie wpisów (Baza wiedzy) i stronach termów `oferta` i `branza`; pozostałe strony mają wyłącznie domyślną regułę title.
- **[9pegz7]** Blok otwierający strony — pierwszy blok treści wpisu (pierwszy blok z nazwą; odstępy i luźny tekst lub HTML między blokami pomijane); z niego pochodzą lead (meta description) i obraz (`og:image`). Strona wpisów i branża — blok otwierający sekcji (`baza-wiedzy`, `branza-<slug termu>`, opublikowanej, rozwiązanej przez abstrakcję tłumaczeń); brak sekcji — bez leadu i obrazu.

## Pola nadpisania

- **[jsncvy]** Pola „Tytuł dla wyszukiwarek" (meta `_feuer_seo_tytul`, jednowierszowe) i „Opis dla wyszukiwarek" (`_feuer_seo_opis`, wielowierszowe, podziały wierszy zostają): artykuły, strony, produkty — panel „Wyszukiwarka" w panelu dokumentu edytora (skrypt panelu ładowany tylko dla tych typów; zapis razem z wpisem); termy `oferta` i `branza` — formularz termu (dodawanie i edycja); Baza wiedzy — pola strony z wpisami. Domyślnie puste; bez limitu długości i licznika znaków.
- **[6ey8yg]** Podpowiedzi pól: tytuł — „Puste — tytuł strony z sufiksem „ – Feuer" (razem do 60 znaków)." (w formularzu termu — „nazwa z sufiksem"); opis — „Puste — opis z tekstu wprowadzającego strony."
- **[9qymn6]** Meta SEO wpisów i termów w REST API; uprawnienia zapisu — [uprawnienia.md](uprawnienia.md), [pgxvxr].
- **[hz4wf5]** Pola SEO wpisów nie są synchronizowane między tłumaczeniami — każda wersja językowa ma własne wartości ([wielojezycznosc.md](wielojezycznosc.md), [jrtygf]); pola termów `oferta` i `branza` są wspólne dla języków ([wielojezycznosc.md](wielojezycznosc.md), [7n3mcs]).

## Title

- **[uburyk]** Title: tytuł strony + sufiks „ – Feuer" (stały tekst, niezależny od nazwy witryny); gdy tytuł (tekst bez HTML) z sufiksem przekracza 60 znaków — bez sufiksu. Bez opisu witryny (tagline), także na stronie głównej; opis witryny (`blogdescription`) jest pusty.
- **[68km3k]** Tytuł strony: tytuł wpisu albo nazwa termu; strona główna — nazwa witryny (infrastruktura.md, [eaqenh]).
- **[9pc6ea]** Nadpisanie: pole „Tytuł dla wyszukiwarek" — cały title, bez sufiksu (i bez numeru strony archiwum); puste — reguła domyślna. Strona główna ma nadpisanie „Feuer – szkolenia i obsługa BHP oraz ppoż. dla firm".
- **[jtmkg6]** Kolejne strony stronicowanego archiwum `oferta` lub `branza` (`/page/N/`): title „<tytuł> – Strona N – Feuer"; numer strony nie wlicza się do limitu 60 znaków.

## Meta description

- **[kunsbt]** Generowana z leadu bloku otwierającego:

  | ID | Blok otwierający | Lead |
  |---|---|---|
  | **[cxyaf6]** | Top visual produktowy (szkolenie, usługa) | pole „lead" (obowiązkowe) |
  | **[ny4aej]** | Top visual listingu („Oferta", strony lądowania) | pole „lead" |
  | **[7pb9ae]** | Top visual kontentowy (strony filarów, „O firmie", sekcje branży i Bazy wiedzy) | pierwszy w kolejności dokumentu akapit `core/paragraph` w stylu „Lead" (`is-style-wstep`) wśród bloków wewnętrznych, także zagnieżdżonych (np. w „Dwie kolumny"); brak — lead pusty |
  | **[uyrfn3]** | Karty informacyjne na zdjęciu (hero strony głównej) | pierwsza linia tekstu na pasie oznaczona jako „lead" |

- **[gckm7m]** Wyjątki: artykuł — zajawka (excerpt); kategoria oferty — opis termu (lead Top visualu listingu); branża — lead bloku otwierającego sekcji branży, nie opis termu (opis termu to podpis kafelka branży); Baza wiedzy — lead bloku otwierającego sekcji `baza-wiedzy`.
- **[u2sktw]** Tekst leadu: czysty tekst w jednej linii (`<br>` → spacja, znaczniki usunięte, encje zdekodowane, białe znaki — także twarda spacja — zwinięte, brzegi przycięte); do 155 znaków — w całości, dłuższy — skracany do ok. 155 znaków na granicy słowa, z „…"; przed „…" obcinane końcowe białe znaki i `,;:.–-` (inne znaki, np. `!`, `?`, zostają).
- **[rxhwxn]** Nadpisanie: pole „Opis dla wyszukiwarek" — w całości, bez skracania (także ponad 155 znaków) i bez normalizacji białych znaków; puste — lead.
- **[9ugkzz]** Pusty wynik (brak leadu, inny blok otwierający, wpis bez bloków — np. „Polityka bezpieczeństwa", „Dane osobowe") — bez `<meta name="description">`; snippet układa Google.
- **[r896gf]** Kategorie oferty bez opisu termu mają meta description z pola „Opis dla wyszukiwarek" (teksty wpisane na produkcji przez agenta, bez weryfikacji merytorycznej).

## OG / Twitter

- **[f8qnn4]** Znaczniki: `og:type` (`article` — artykuł, `website` — pozostałe), `og:url` = adres kanoniczny, `og:title` = title (z sufiksem albo nadpisaniem), `og:description` = meta description, `og:image` z `og:image:width` i `og:image:height`; `twitter:card` = `summary_large_image` — tytuł, opis i obraz Twitter bierze z OG (bez `twitter:title`, `twitter:description`, `twitter:image`). Znacznik z pustą wartością nie jest wypisywany; wartości — znakami, nie encjami (np. „–", nie `&#8211;`).
- **[76uv3j]** `og:image` — obraz strony w pełnym rozmiarze (oryginał JPEG / PNG, nie miniatura AVIF), wymiary z pliku:

  | ID | Strona / blok otwierający | Obraz |
  |---|---|---|
  | **[e7bxy6]** | Top visual kontentowy | plakat filmu bloku (plik desktop); bez filmu albo plakatu — obrazek wyróżniający wpisu (strona wpisów, branża — sekcji) |
  | **[ht39a9]** | Top visual produktowy | obrazek wyróżniający wpisu (film bloku nieuwzględniany) |
  | **[gj28n4]** | Top visual listingu | zdjęcie bloku (0 — brak obrazu) |
  | **[5gw94g]** | Karty informacyjne na zdjęciu | medium „film" — plakat filmu (plik desktop; film bez plakatu — brak obrazu); inaczej zdjęcie bloku |
  | **[2uzycv]** | Artykuł | obrazek wyróżniający artykułu |
  | **[w3xwvs]** | Kategoria oferty | zdjęcie termu (`_feuer_zdjecie`); brak — zdjęcie kategorii bezpośrednio nadrzędnej (jeden poziom) |

- **[gcd4yk]** Plakat filmu — [media.md](media.md), [my9z2h]; dla pliku innego typu niż `video/mp4` albo bez obrazka wyróżniającego — brak plakatu.
- **[kvb8x4]** Brak obrazu (także artykuł bez obrazka wyróżniającego — nie obraz zastępczy artykułu — i strona, której blok otwierający nie jest w tabeli, np. Belka informacyjna: zdjęcie ani film bloku nie są użyte) — obraz domyślny motywu `img/og-domyslny.jpg`: kadr hero strony głównej (plakat filmu) przycięty do 1200×630; wymiary 1200×630 wpisane w kodzie na stałe.

## Canonical

- **[aejyat]** Adres kanoniczny (canonical i `og:url`): adres własny, absolutny, bez parametrów zapytania (np. `?termin=`) — strona wpisów: jej adres; wpis: adres kanoniczny rdzenia WordPressa; term: adres termu.
- **[ntw22f]** Własny `<link rel="canonical">` — wyłącznie strona wpisów (`/baza-wiedzy/`) i archiwa `oferta` i `branza`; strony pojedyncze — canonical rdzenia WordPressa. Kolejne strony stronicowanego archiwum (`/page/N/`) mają canonical i `og:url` pierwszej strony archiwum.

## hreflang

- **[bz5nmq]** Polylang emituje hreflang automatycznie (bez kodu projektu): strona główna — `hreflang="pl"` (`/`) i `hreflang="en"` (`/en/`) na wszystkich środowiskach, choć na produkcji `/en/` przekierowuje 301 na `/`; podstrony (bez tłumaczeń) — bez hreflang.

## Indeksowanie

- **[9r42p8]** Produkcja otwarta dla wyszukiwarek: `blog_public` = 1, vhost bez `X-Robots-Tag`, strony z `robots` `max-image-preview:large` (bez noindex). `robots.txt` — wirtualny WordPressa: `Disallow: /wp-admin/`, `Allow: /wp-admin/admin-ajax.php`, `Sitemap: https://www.feuer.pl/wp-sitemap.xml`; bez filtra projektu.
- **[8c2bc9]** Treści `robots.txt` nie edytuje się w panelu — plik wirtualny rdzenia bez filtra projektu (zmiana = zmiana kodu). „Widoczność dla wyszukiwarek" (`blog_public`, Ustawienia → Czytanie) = 0 przełącza rdzeń na `Disallow: /` i noindex; serwer dev — [ehyrq9].
- **[4xtas2]** Archiwa rubryk (`category`) — `noindex` (rubryki nie należą do struktury serwisu; listę artykułów daje `/baza-wiedzy/`); strona błędu serwera — `noindex`.

## Sitemapa

- **[br46r3]** Sitemapa rdzenia WordPressa (`wp-sitemap.xml`) z filtrami wtyczki; adresy `www.feuer.pl`.
- **[t7e6hx]** Sitemapa obejmuje strony, artykuły, produkty oraz termy `oferta` i `branza` ([uun5vw]); typy niepubliczne `sekcja` i `ekspert` — poza nią.
- **[ea4jue]** Bez sitemapy użytkowników (`wp-sitemap-users-*`, także `/en/` — 404; indeks bez dostawcy `users`) — ujawniałaby loginy i nazwiska kont.
- **[eru3m4]** Bez strony „Kontakt" (slug `kontakt` w języku żądania) — jej wejście robi 301 na „O firmie" (formularz-kontaktu.md).
- **[j22wuz]** Bez taksonomii rubryk (`category`); taksonomie niepubliczne (`oznaczenie`, `grupa`) poza sitemapą z zasady WordPressa.
- **[uun5vw]** Termy `oferta` i `branza` — wyłącznie z przypiętymi produktami (zachowanie WordPressa): kategoria z produktami tylko w podkategoriach (np. kategorie najwyższego poziomu) jest poza sitemapą.

## Dane strukturalne

- **[zejpf8]** JSON-LD schema.org wyłącznie trzech typów: `Organization`, `BreadcrumbList` (`includes/dane-strukturalne.php`) i `FAQPage` (render bloku FAQ); bez `WebSite`, `Article`, `Course`, `Event`.
- **[5z3ut5]** Każdy zestaw — osobny skrypt `application/ld+json` z `@context` `https://schema.org`; JSON ze znakami Unicode i ukośnikami bez escapowania, `<` i `>` jako `<`, `>` (treść nie zamknie znacznika `<script>`).

### Organization

- **[8mza78]** Wyłącznie strona główna, w `<head>` (`wp_head`).
- **[23bkfp]** Właściwości: `name` — nazwa witryny (encje zdekodowane); `url` — adres strony głównej; `logo` — ikona witryny ([strony.md](strony.md), [4qcyr9]; logo wtyczki 179×30 jest poniżej minimum Google 112×112); `legalName`, `taxID` (NIP), `email` — dane organizacji ([ustawienia.md](ustawienia.md), [p3qxtw]); `telephone` — lista numerów z pola „Telefony" (wiersz = numer, przycięty, puste pomijane; lista także przy jednym numerze); `sameAs` — linki social stopki ([ustawienia.md](ustawienia.md), [rrgwk9]), w kolejności opcji.
- **[s46dc3]** `address` — `PostalAddress`: `streetAddress`, `postalCode`, `addressLocality` i stałe `addressCountry` = `PL`; wystawiane, gdy wypełnione jest co najmniej jedno z trzech pól (puste pomijane).
- **[7rctfw]** Puste pole (także brak ikony witryny albo linków social) — bez właściwości, nie pusta wartość.
- **[hh2u3u]** Bez `image` (to zdjęcie firmy, nie logo) — niekrytyczna uwaga Rich Results Test („Local businesses") zostaje.

### BreadcrumbList

- **[kcpv6v]** Strony z niepustą ścieżką okruszków wypisaną przez blok okruszków albo sekcję otwierającą (rząd okruszków lub link wstecz): każde wypisanie ścieżki wywołuje akcję `feuer_okruszki`; skrypt — raz na stronę (pierwsze wywołanie), w stopce strony (`wp_footer`). Strona główna, archiwa rubryk i tagów, wyniki wyszukiwania, 404 — bez ścieżki, bez danych.
- **[cxp9q2]** Pozycje: trasa widocznych okruszków ([nawigacja.md](nawigacja.md)) poprzedzona „Strona główna"; `position` od 1; każda pozycja, także bieżąca strona, z `name` (czysty tekst, encje zdekodowane) i `item` (adres).

### FAQPage

- **[hyah87]** Blok FAQ emituje jeden skrypt `FAQPage` (`mainEntity`: `Question` z `acceptedAnswer` typu `Answer`) wewnątrz sekcji FAQ — skrypt obok sekcji rozbiłby selektory sąsiedztwa (`.faq + .sekcja-kontaktowa`); tylko gdy jest co najmniej jedno pytanie z treścią.
- **[vejpah]** Pytanie (`name`) — czysty tekst (bez znaczników, encje zdekodowane, przycięty); odpowiedź (`acceptedAnswer.text`) — ponowny render bloków odpowiedzi oczyszczony do znaczników dozwolonych przez Google: `p`, `ul`, `ol`, `li`, `a` (tylko `href`), `strong`, `em`, `br` (inne znaczniki usuwane, tekst zostaje).
- **[p9qyt3]** Pozycja z pustym pytaniem albo pustą odpowiedzią (po usunięciu znaczników) nie trafia do JSON-LD — znacznik `<wprowadź dane>` nie wchodzi do danych.
