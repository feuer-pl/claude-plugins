# feuer/dane-kontaktu

„Dane kontaktu" — dane kontaktu karty bloku [feuer/sekcja-kontaktowa](blok-sekcja-kontaktowa.md): jeden tekst formatowany wspólny dla serwisu, w sekcji `dane-kontaktu`. Typ: T ([bloki.md](bloki.md), „Typy bloków"). Sekcja i blokada struktury: [sekcje.md](sekcje.md), [4t826x].

## Gdzie

- **[zq3wp4]** Wyłącznie w sekcji `dane-kontaktu`: poza wstawiaczem, raz w treści (`multiple: false`), bez zapisu jako blok wielokrotnego użytku ([bloki.md](bloki.md), [ecp7bd]).
- **[ms4n8m]** Zmiana danych zmienia kartę Sekcji kontaktowej na wszystkich stronach; osobnych pól (nazwa, rola, telefon, e-mail) nie ma.

## Pola

| ID | Pole | Atrybut | Rodzaj | Dozwolone | Limit | Wymagane / domyślne |
|---|---|---|---|---|---|---|
| **[vzq94m]** | Dane kontaktu (adres, telefony, e-mail) | bloki wewnętrzne | strefa treści (tekst formatowany — [bloki.md](bloki.md), [c3atk4]) | skład wg [bloki.md](bloki.md), [rg4r9f]; łamanie wiersza Shift+Enter | — | obowiązkowe — puste dane albo brak sekcji: na karcie znacznik `<wprowadź dane>` |

## Dane

- **[74uk6m]** Blok statyczny bez własnego renderu (`save` zapisuje bloki wewnętrzne): dane renderuje blok `feuer/sekcja-kontaktowa`.
- **[5xfght]** Treść początkowa sekcji (tytuł „Dane kontaktu"; [sekcje.md](sekcje.md), [rrzbuy]) wg przykładu niżej — adres, telefony w jednym wierszu po przecinku (bez linków, numery pogrubione), e-mail z linkiem; np. WP-CLI `wp post create - --post_type=sekcja --post_title="Dane kontaktu" --post_name=dane-kontaktu --post_status=publish` z treścią na wejściu.

## Edytor

- **[zzuvgs]** Lustrzany markup karty z edycją danych w miejscu; nagłówek („Porozmawiajmy o bezpiecznym starcie") i przycisk („Formularz kontaktowy") — teksty domyślne bez edycji (to pola każdego bloku Sekcja kontaktowa z osobna). Przycisk zostaje w podglądzie, bo na desktopie wyznacza szerokość kolumny danych (`white-space: nowrap`) — bez niego podgląd łamałby wiersz telefonów.
- **[eu7ku2]** Wrapper w edytorze sekcji bez klasy `sekcja-kontaktowa` — inaczej łapie regułę bloku ostatniego w treści (szary pas pod kartą).

## Przykład

```html
<!-- wp:feuer/dane-kontaktu -->
<!-- wp:paragraph -->
<p>ul. Mickiewicza 32/3<br>01-616 Warszawa<br>+48 <strong>22 618 64 35</strong>, +48 <strong>733 777 115</strong><br><a href="mailto:feuer@feuer.pl">feuer@feuer.pl</a></p>
<!-- /wp:paragraph -->
<!-- /wp:feuer/dane-kontaktu -->
```
