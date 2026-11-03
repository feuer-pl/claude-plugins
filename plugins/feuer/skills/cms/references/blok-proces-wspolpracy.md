# feuer/proces-wspolpracy

„Proces współpracy" — sekcja na tle wyróżnionym: opcjonalny nagłówek i rząd numerowanych kroków ([feuer/proces-wspolpracy-krok](blok-proces-wspolpracy-krok.md)), w odmianie „Proces" albo „Lista". Typ: T ([bloki.md](bloki.md), „Typy bloków"); reguły wspólne pozycji: [bloki.md](bloki.md), „Pozycje".

## Gdzie

- **[k8yarb]** Samodzielna sekcja pełnej szerokości w treści stron i produktów, poza paletą treści redakcyjnej.
- **[y4f8tk]** Pusty nagłówek bloku — nagłówek sekcji: [README szare-tlo](blok-szare-tlo.md), [q2bap3].

## Pola

| ID | Pole | Atrybut | Rodzaj | Dozwolone | Limit | Wymagane / domyślne |
|---|---|---|---|---|---|---|
| **[n7tmqs]** | Nagłówek (H2, w całości ExtraBold) | `tytul` | tekst z łamaniem wiersza | „Akcent w nagłówkach — bez akcentu" ([bloki.md](bloki.md), [bmw7u4]) | 45 | opcjonalne, bez tekstu domyślnego — pusty (także same łamania wiersza): blok bez `h2`, zaczyna się od rzędu kroków |
| **[bm7bf2]** | Odmiana | `odmiana` | wybór w toolbarze bloku: „Proces" (1), „Lista" (2) | 1, 2 | — | 1 — także bloki bez atrybutu |
| **[8cq7n9]** | Kroki | bloki wewnętrzne | `feuer/proces-wspolpracy-krok` | wyłącznie `feuer/proces-wspolpracy-krok` | „Liczba kroków" w toolbarze bloku ([bloki.md](bloki.md), [4dtarj], [edg7dw]) | po wstawieniu 4 |
| **[mnrctm]** | Szerokość tła | `szerokoscTla` | panel „Ustawienia" — wspólne ustawienie szerokości tła: css.md, [k34pyh] | `1440`, `1920` | — | `1440` |

- **[xpas5g]** Bez leadu i podpisu — atrybuty bloku to wyłącznie `tytul` i `odmiana`.

## Warianty

- **[436ved]** „Proces" — nad opisem każdego kroku linia marki ze strzałką (kolejne kroki); „Lista" — ta sama linia bez grotu (pozycje bez kolejności), klasa `proces-lista` na sekcji (front i edytor); reszta wyglądu wspólna.

## Dane

- **[nnk59f]** Skład: `section.proces.tlo-wyroznione` z kontenerem — opcjonalny `h2.proces-tytul` i lista numerowana `ol.proces-kroki` z krokami.

## Edytor

- **[u5ryqd]** Pole nagłówka widoczne, gdy ma treść albo blok jest zaznaczony (pusty z podpowiedzią „Nagłówek (opcjonalny)…"); poza zaznaczeniem pusty nagłówek niewidoczny — kanwa = front.

## Przykład

```html
<!-- wp:feuer/proces-wspolpracy {"tytul":"Jak wygląda współpraca?"} -->
<!-- wp:feuer/proces-wspolpracy-krok {"tytul":"Dobór i role koordynatorów","opis":"Pomagamy dobrać właściwe osoby i podzielić obiekt na obszary odpowiedzialności, tak by każde piętro lub strefa miały swojego lidera."} /-->
<!-- wp:feuer/proces-wspolpracy-krok {"tytul":"Plan ewakuacji i procedury","opis":"Przygotowujemy lub aktualizujemy plan ewakuacji spójny z instrukcją bezpieczeństwa pożarowego oraz zasady komunikacji."} /-->
<!-- wp:feuer/proces-wspolpracy-krok {"tytul":"Szkolenie i scenariusze","opis":"Szkolimy koordynatorów praktycznie, kierowanie grupą, sprawdzanie pomieszczeń, liczenie i współpraca ze strażą, na realistycznych scenariuszach."} /-->
<!-- wp:feuer/proces-wspolpracy-krok {"tytul":"Próbna ewakuacja","opis":"Planujemy i przeprowadzamy próbną ewakuację jako sprawdzian przygotowania koordynatorów i całej organizacji."} /-->
<!-- /wp:feuer/proces-wspolpracy -->
```
