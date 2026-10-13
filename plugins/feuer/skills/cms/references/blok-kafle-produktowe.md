# feuer/kafle-produktowe

„Kafle produktowe" — sekcja na tle wyróżnionym z grupą produktów: nagłówek, wprowadzenie, siatka kart produktów i kafel kontaktowy na końcu. Typ: D + T ([bloki.md](bloki.md), „Typy bloków"). Grupa i karta produktu: [strony-zbiorcze.md](strony-zbiorcze.md), [ty4cwk], [kejzfv]; listing strony branży: [strony-zbiorcze.md](strony-zbiorcze.md), „Strona branży"; źródła i wybór ręczny: [bloki.md](bloki.md), „Źródła pozycji".

## Gdzie

- **[ksheg3]** Samodzielna sekcja w treści stron (strony filarów, strony lądowania), w dowolnej liczbie na stronie; na stronie branży — w sekcji branży wg zestawu startowego ([sekcje.md](sekcje.md), [8h54zx]).

## Pola

| ID | Pole | Atrybut | Rodzaj | Dozwolone | Limit | Wymagane / domyślne |
|---|---|---|---|---|---|---|
| **[2rpfkv]** | Nagłówek (H2, w całości ExtraBold) | `tytul` | tekst z łamaniem wiersza, w miejscu | „Akcent w nagłówkach — bez akcentu" ([bloki.md](bloki.md), [bmw7u4]) | 55 | obowiązkowe |
| **[6t5t4d]** | Wprowadzenie (typografia A40, `.tresc`) | bloki wewnętrzne | strefa treści (tekst formatowany — [bloki.md](bloki.md), [c3atk4]) | skład wg [bloki.md](bloki.md), [rg4r9f] | — | opcjonalne — bez tekstu się nie wyświetla |
| **[5m9p6e]** | Źródło produktów | `zrodlo` + `produkty` (ID), `oferta` (ID termu), `branza` (ID termu), `miesiace` (slugi) | panel „Ustawienia": „Źródło produktów" — „Wybór ręczny", „Kategoria oferty", „Branża", „TOP 20", „Miesiące"; dla źródła „branża bieżącej strony" (`branza-strony`) wyboru nie ma | — | bez limitu liczby kart | wybór ręczny z pustą listą |
| **[wcef4q]** | Kafel kontaktowy na końcu | `kontakt` | przełącznik (panel „Ustawienia"), pomoc „Ostatni kafel siatki otwiera formularz kontaktu." | — | — | włączony |
| **[kf7u3n]** | Tytuł, tekst i tekst linku kafla kontaktowego | `kontaktTytul`, `kontaktTekst`, `kontaktLink` | w miejscu: tytuł i tekst z łamaniem wiersza, tekst linku jednowierszowy | bez formatów w edytorze; na froncie tytuł i tekst oczyszczane do pogrubienia, kursywy i łamania | — | puste — teksty domyślne (i18n): „Inne potrzeby? / I tak mamy to, serio", „Pomożemy Ci wybrać odpowiednie szkolenie lub przygotujemy dedykowaną ofertę.", „Skontaktuj się z nami" |

## Dane

- **[mbmw3z]** Źródła: kategoria oferty — produkty kategorii z podkategoriami (0 — brak produktów); branża — produkty wskazanej branży oraz produkty bez branży (0 — brak; [taksonomie.md](taksonomie.md), [82fpks]); branża bieżącej strony — jak „branża", dla branży sekcji `branza-<slug>`, w której stoi blok (kontekst `postId`); TOP 20 — produkty z oznaczeniem „TOP 20"; miesiące — produkty oznaczone którymkolwiek z wybranych miesięcy (nieznane slugi odrzucane). Źródła automatyczne — lista listingu ([strony-zbiorcze.md](strony-zbiorcze.md), [hu253v]); wybór ręczny — wskazane opublikowane produkty w kolejności listy, niezależnie od flagi „Nie pokazuj w listingu kategorii" ([produkt.md](produkt.md), [999uaf]).
- **[j3buwb]** Kafel kontaktowy (ikona zaszyta) — ostatnia pozycja siatki, otwiera layer kontaktu (formularz-kontaktu.md, [bgjywv]); istnieje tylko w tym bloku (strony filarów, sekcje branż).
- **[e356e5]** Brak produktów — zachowanie wg [bloki.md](bloki.md), [szj5f5]; kafel kontaktowy też się nie renderuje.
- **[w4bwtw]** Słownik miesięcy dla panelu pochodzi z renderu bloku (`feuer_oznaczenia()`, dane `feuer_dane`); powód — [taksonomie.md](taksonomie.md), [q5uanq].

## Edytor

- **[bdb2v4]** Panel: „Kategoria oferty" — „— wybierz —" (0) i kategorie z wcięciami ([bloki.md](bloki.md), [ck9xys]); „Branża" — „— wybierz —" i wszystkie branże, podpowiedź o produktach bez branży; „Miesiące" — pola wyboru miesięcy ze słownika oznaczeń (bez „TOP 20", w kolejności kalendarza).
- **[j9hmqe]** Puste wprowadzenie (brak bloków albo same puste akapity) ukryte, dopóki blok ani jego akapit nie jest zaznaczony; pusty akapit z podpowiedzią; wprowadzenie bez bloków dostaje z powrotem pusty akapit (poza podglądem we wstawiaczu), po wstawieniu jest jeden.
- **[hzdbg7]** Brak produktów — w miejscu kart komunikat wg źródła, np. wybór ręczny: „Brak produktów do pokazania — wybierz produkty w ustawieniach bloku. Na stronie blok się nie wyświetla."; branża bieżącej strony: „…działa wyłącznie w sekcji branży…".
- **[h9bdbh]** Zapis w treści: atrybuty i bloki wewnętrzne wprowadzenia (`save` = `InnerBlocks.Content`).

## Przykład

```html
<!-- wp:feuer/kafle-produktowe {"tytul":"Bezpieczny start nowej firmy i inwestycji","produkty":[146,150,152]} -->
<!-- wp:paragraph -->
<p>Najtańszy błąd BHP to ten, którego nie popełniono. Nowym firmom uruchamiamy BHP od pierwszego pracownika.</p>
<!-- /wp:paragraph -->
<!-- /wp:feuer/kafle-produktowe -->

<!-- wp:feuer/kafle-produktowe {"tytul":"Szkolenia na zimę","zrodlo":"miesiace","miesiace":["grudzien","styczen","luty"],"kontakt":false} -->
<!-- wp:paragraph -->
<p>Szkolenia, które warto zaplanować na sezon grzewczy.</p>
<!-- /wp:paragraph -->
<!-- /wp:feuer/kafle-produktowe -->
```
