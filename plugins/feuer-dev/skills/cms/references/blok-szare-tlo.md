# feuer/szare-tlo

„Szare tło" — pas tła wyróżnionego na całą szerokość strony, wewnątrz bloki palety treści redakcyjnej. Typ: T ([bloki.md](bloki.md), „Typy bloków"); przyjmuje paletę, ale do niej nie należy ([paleta-tresci.md](paleta-tresci.md), [7dr2f7]).

## Gdzie

- **[4qxsgd]** Treść wpisu, między sekcjami, obok bloków palety w korzeniu treści; strefy treści bloków go nie przyjmują ([paleta-tresci.md](paleta-tresci.md), [7dr2f7]). Ograniczenia typu wpisu nie ma — blok da się wstawić także w artykuł.
- **[q2bap3]** Zastosowanie: sekcję na szarym tle bez własnego nagłówka (np. Proces współpracy) otacza się Szarym tłem z nagłówkiem, leadem albo zdaniem podsumowującym (akapit w stylu „Hasło") nad nią albo pod nią — powstaje jedno ciągłe tło.

## Pola

| ID | Pole | Atrybut | Rodzaj | Dozwolone | Limit | Wymagane / domyślne |
|---|---|---|---|---|---|---|
| **[skw45n]** | Treść | bloki wewnętrzne | strefa treści, swobodna (szablon niezablokowany); typografia treści redakcyjnej (A40, `.tresc`) | paleta treści redakcyjnej ([paleta-tresci.md](paleta-tresci.md), [8psccg]) | — | obowiązkowe; po wstawieniu jeden pusty akapit z podpowiedzią `<wprowadź dane>` |
| **[9ddfg3]** | Szerokość tła | `szerokoscTla` | panel „Ustawienia" — wspólne ustawienie szerokości tła: css.md, [k34pyh] | `1440`, `1920` | — | `1440` |

## Dane

- **[fqq7c6]** Brak treści (także same puste akapity) — w miejscu treści znacznik `<wprowadź dane>` na froncie i w edytorze; samo zdjęcie (`<img>` bez tekstu) jest treścią.
- **[h2rppn]** Z sąsiednią sekcją na szarym tle (klasa `tlo-wyroznione`) jedno ciągłe tło: pod taką sekcją bez górnego odstępu, nad taką sekcją (inną niż Szare tło) bez dolnego — odstęp daje sąsiad; dwa Szare tła pod sobą dzieli jeden odstęp (dolny pierwszego).

## Edytor

- **[f3xnm3]** Wstawiacz w środku nie oferuje „Własnego HTML" (poza paletą): istniejący blok HTML jest poprawny, nowy wstawia się przez edytor kodu.

## Przykład

```html
<!-- wp:feuer/szare-tlo -->
<!-- wp:heading -->
<h2 class="wp-block-heading">Zarządzanie przez<br><span class="akcent-marki">bezpieczeństwo.</span></h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>Pomagamy firmom, które dopiero wchodzą na polski rynek lub otwierają nową lokalizację – i nie chcą tracić czasu na rozszyfrowanie lokalnych przepisów BHP.</p>
<!-- /wp:paragraph -->
<!-- /wp:feuer/szare-tlo -->

<!-- wp:feuer/proces-wspolpracy -->
<!-- wp:feuer/proces-wspolpracy-krok {"tytul":"Procedury i dokumentacja","opis":"Kompletna, aktualna, zrozumiała."} /-->
<!-- wp:feuer/proces-wspolpracy-krok {"tytul":"Regularna weryfikacja","opis":"Audyty, kontrole wewnętrzne, analiza luk."} /-->
<!-- /wp:feuer/proces-wspolpracy -->

<!-- wp:feuer/szare-tlo -->
<!-- wp:paragraph {"className":"is-style-haslo"} -->
<p class="is-style-haslo">Mniej wypadków, niższe koszty operacyjne, większe zadowolenie pracowników, gotowość do ESG.</p>
<!-- /wp:paragraph -->
<!-- /wp:feuer/szare-tlo -->
```
