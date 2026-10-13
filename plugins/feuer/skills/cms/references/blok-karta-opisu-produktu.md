# feuer/karta-opisu-produktu

„Karta opisu produktu" (w projekcie „Program") — nagłówek sekcji i 2, 3, 4 albo 6 etapów ([feuer/karta-opisu-produktu-pozycja](blok-karta-opisu-produktu-pozycja.md)) w odmianie „Zakładki" albo „Kolumny". Typ: T ([bloki.md](bloki.md), „Typy bloków"); reguły wspólne pozycji: [bloki.md](bloki.md), „Pozycje"; zakładki i akordeon: [bloki.md](bloki.md), „Zakładki i akordeon".

## Gdzie

- **[szbap9]** Samodzielna sekcja pełnej szerokości w treści produktów i stron, poza paletą treści redakcyjnej; nazwa bloku nie zawęża osadzenia.
- **[rb9rzw]** Osobny komponent, nie wariant rodziny „rząd pozycji" (Dla kogo, Proces współpracy) — inny sposób redagowania treści (etap z treścią redakcyjną).

## Pola

| ID | Pole | Atrybut | Rodzaj | Dozwolone | Limit | Wymagane / domyślne |
|---|---|---|---|---|---|---|
| **[gxfzus]** | Nagłówek (H2, w całości ExtraBold) | `tytul` | tekst z łamaniem wiersza | „Akcent w nagłówkach — bez akcentu" ([bloki.md](bloki.md), [bmw7u4]) | 45 | obowiązkowe |
| **[fvdwvw]** | Odmiana | `odmiana` | wybór w toolbarze: „Zakładki" (1), „Kolumny" (2); ta sama treść etapów w obu | 1, 2 | — | 1 |
| **[seuure]** | Etapy | bloki wewnętrzne | `feuer/karta-opisu-produktu-pozycja` | wyłącznie `feuer/karta-opisu-produktu-pozycja` | przyciski w toolbarze (podpowiedź „Liczba etapów: N"; [bloki.md](bloki.md), [4dtarj], [edg7dw]) | po wstawieniu 4 puste etapy |

## Warianty

- **[fjxkkh]** „Zakładki" (1): pionowe zakładki etapów z lewej (nadtytuł i tytuł) i panel treści z prawej, klik w zakładkę przełącza panel; poniżej 1024 px — akordeon (panel pod nagłówkiem etapu). „Kolumny" (2): statyczny rząd kolumn równej szerokości (`ol` / `li`), bez zakładek i akordeonu; poniżej 1024 px jedna kolumna.

## Dane

- **[7bcr2y]** Rodzic przekazuje odmianę etapom kontekstem `feuer/odmiana`; etap bez kontekstu zachowuje się jak „Zakładki".
- **[8bv6vc]** Etapy zapisane jako bloki wewnętrzne (`save` = `InnerBlocks.Content`); front renderuje blok po stronie serwera z gotową treścią etapów: „Zakładki" — `div.program-etapy` z `data-zakladki` (moduł `feuer-zakladki` w trybie domyślnym), „Kolumny" — `ol.program-rzad`.
- **[6jhzqc]** „Zakładki": etapy renderują się nieaktywne, rodzic aktywuje pierwszy (zakładka `aria-expanded="true"`, panel bez `hidden`).

## Edytor

- **[xctdtp]** „Zakładki" w edytorze jak na froncie ([bloki.md](bloki.md), [8jw4ud]): widoczny panel zaznaczonego etapu (etap zaznaczony albo blok w jego treści; klik w zakładkę zaznacza etap), bez zaznaczenia w bloku — etap I, pozostałe panele `hidden`; w podglądzie mobile akordeon z rozwiniętym tylko zaznaczonym etapem. „Kolumny": wszystkie etapy widoczne.

## Przykład

```html
<!-- wp:feuer/karta-opisu-produktu {"tytul":"Wsparcie na każdym etapie rozwoju"} -->
<!-- wp:feuer/karta-opisu-produktu-pozycja {"nadtytul":"Etap I","tytul":"Planowanie i projektowanie"} -->
<!-- wp:paragraph -->
<p>Na etapie budowy lub adaptacji obiektu BHP to moment, w którym błędy kosztują najwięcej.</p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul class="wp-block-list"><!-- wp:list-item -->
<li>konsultacje BHP podczas wyboru lokalizacji,</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>doradztwo w zakresie wymaganych pozwoleń i certyfikacji.</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:buttons -->
<div class="wp-block-buttons"><!-- wp:button {"className":"is-style-link-strzalka"} -->
<div class="wp-block-button is-style-link-strzalka"><a class="wp-block-button__link wp-element-button">Sprawdź całą ofertę e-sklepu</a></div>
<!-- /wp:button --></div>
<!-- /wp:buttons -->
<!-- /wp:feuer/karta-opisu-produktu-pozycja -->

<!-- wp:feuer/karta-opisu-produktu-pozycja {"nadtytul":"Etap II","tytul":"Budowa lub adaptacja"} -->
<!-- wp:paragraph -->
<p>Budowa i adaptacja to czas, w którym na placu spotykają się wykonawcy, dostawcy i pierwsi pracownicy.</p>
<!-- /wp:paragraph -->
<!-- /wp:feuer/karta-opisu-produktu-pozycja -->

<!-- wp:feuer/karta-opisu-produktu-pozycja {"nadtytul":"Etap III","tytul":"Organizacja firmy"} -->
<!-- wp:paragraph -->
<p>Firma rusza: zatrudniasz ludzi, ustalasz stanowiska, kupujesz sprzęt.</p>
<!-- /wp:paragraph -->
<!-- /wp:feuer/karta-opisu-produktu-pozycja -->

<!-- wp:feuer/karta-opisu-produktu-pozycja {"nadtytul":"Etap IV","tytul":"Bieżąca obsługa i rozwój"} -->
<!-- wp:paragraph -->
<p>Zakład działa, a przepisy i ludzie się zmieniają.</p>
<!-- /wp:paragraph -->
<!-- /wp:feuer/karta-opisu-produktu-pozycja -->
<!-- /wp:feuer/karta-opisu-produktu -->
```
