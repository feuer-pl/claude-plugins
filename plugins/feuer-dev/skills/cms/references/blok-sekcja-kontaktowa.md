# feuer/sekcja-kontaktowa

„Sekcja kontaktowa" — karta kontaktu: nagłówek, awatar (znak Feuer), dane kontaktu wspólne dla serwisu i przycisk otwierający layer kontaktu. Typ: T ([bloki.md](bloki.md), „Typy bloków"). Dane kontaktu: [feuer/dane-kontaktu](blok-dane-kontaktu.md); layer kontaktu i prewypełnienie: formularz-kontaktu.md; sekcje `kontakt-kategorii`, `kontakt-artykulu`: [sekcje.md](sekcje.md).

## Gdzie

- **[py9dyj]** Samodzielna sekcja w treści stron i produktów, poza paletą treści redakcyjnej; także strony systemowe — kategoria (sekcja `kontakt-kategorii`), artykuł (`kontakt-artykulu`), Baza wiedzy; liczba bloków na stronie bez ograniczeń; ograniczenia typu strony nie ma.
- **[x9fgn4]** „Karta kontaktu (Biuro obsługi)" i „Sekcja kontaktowa" to jeden blok.

## Pola

| ID | Pole | Atrybut | Rodzaj | Dozwolone | Limit | Wymagane / domyślne |
|---|---|---|---|---|---|---|
| **[uvyv2m]** | Nagłówek (H2) | `tytul` | tekst z łamaniem wiersza, w miejscu (bez pól w panelu) | „Akcent w nagłówkach" ([bloki.md](bloki.md), [s56shy]) | bez limitu | pusty — „Porozmawiajmy o bezpiecznym starcie" (i18n, twarda spacja po „o"), na froncie i w edytorze |
| **[8c5de4]** | Tekst przycisku | `przycisk` | tekst jednowierszowy, w miejscu | bez formatów | bez limitu | pusty — „Formularz kontaktowy" (i18n) |

## Dane

- **[bk8rvs]** Karta: nagłówek z lewej, z prawej awatar (znak Feuer w kole — zaszyty, nieedytowalny), dane kontaktu i przycisk `<button data-layer="layer-kontakt">`.
- **[wba4qe]** Dane kontaktu: pierwszy blok `feuer/dane-kontaktu` z treści opublikowanej sekcji `dane-kontaktu` — jego bloki wewnętrzne w `.karta-kontaktu-tekst.tresc` (typografia A40). Puste dane (po usunięciu znaczników i spacji, także twardych, i zdekodowaniu encji) albo brak sekcji — znacznik `<wprowadź dane>`; nagłówek i przycisk bez zmian.
- **[cfbzjz]** Sekcje `kontakt-kategorii` i `kontakt-artykulu`: treść — jeden blok `feuer/sekcja-kontaktowa` (pola `tytul`, `przycisk`); struktura zablokowana, więc do pustej sekcji bloku nie da się dodać w edytorze — sekcję z blokiem zakłada administrator, np. `printf '<!-- wp:feuer/sekcja-kontaktowa /-->' | wp post create - --post_type=sekcja --post_title="Kontakt artykułu" --post_name=kontakt-artykulu --post_status=publish`.
- **[h3v667]** Nachodzenie karty na szare tło sąsiadów (blok rysuje je sam, bez własnych odstępów — odstępy dają paddingi sąsiadów): dół karty na szarym — gdy następna sekcja ma szare tło albo blok stoi ostatni przed stopką; góra — gdy poprzednia sekcja ma szare tło (także szary pas Belki informacyjnej odmiany 1); szare nad i pod kartą — karta w całości na szarym. Blok ostatni w treści — pod kartą szary pas, tło pasa certyfikatów stopki szare. Te same reguły w edytorze.
- **[cjbrwu]** Szare sekcje rozpoznawane po klasach bloków wypisanych w `css/sekcja-kontaktowa.css` (m.in. Dla kogo, Proces współpracy, FAQ, Zobacz także, Kafle produktowe).

## Edytor

- **[9uvnd3]** Dane kontaktu w kanwie jak na froncie, bez edycji — HTML z `render.php` (JSON z danymi i adresem edycji sekcji).
- **[cpdt42]** Panel boczny „Dane kontaktu": „Dane kontaktu są wspólne dla całego serwisu — zmiana zmienia kartę na wszystkich stronach." i przycisk „Edytuj dane kontaktu" — edytor sekcji w nowej karcie; przycisku nie ma, gdy sekcja nie istnieje, nie jest opublikowana albo użytkownik nie może jej edytować.

## Wielojęzyczność

- **[t3xd9g]** Dane kontaktu — jedna sekcja `dane-kontaktu` dla wszystkich języków ([sekcje.md](sekcje.md), [8bcbuy]).

## Przykład

```html
<!-- wp:feuer/sekcja-kontaktowa /-->

<!-- wp:feuer/sekcja-kontaktowa {"tytul":"Masz pytania o\u0026nbsp;\u003cspan class=\u0022akcent\u0022\u003eszkolenia?\u003c/span\u003e","przycisk":"Napisz do nas"} /-->
```
