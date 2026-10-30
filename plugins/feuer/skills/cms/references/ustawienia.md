# Ustawienia

Globalne ustawienia serwisu: strona Ustawienia → Feuer (linki social, odbiorca formularza kontaktu, cena uprawnienia SEP, koordynatorka formularza zapisu i klucz GUS, dane organizacji) i wykorzystywane ustawienia WordPressa. Przegląd modelu: [model-tresci.md](model-tresci.md).

## Ustawienia → Feuer

- **[wn44bs]** Strona ustawień serwisu — Ustawienia → Feuer (slug `feuer`, nagłówek „Ustawienia serwisu Feuer"), na natywnym API ustawień WordPressa; sekcje w kolejności: „Linki social", „Formularz kontaktowy", „Formularz zapisu na szkolenie", „Dane organizacji".
- **[qa44d9]** Ustawienia to jeden zestaw dla wszystkich języków — zwykłe opcje WordPressa, bez wersji per język.
- **[r7deg8]** Wszystkie sekcje są jednym formularzem z jednym przyciskiem zapisu: zapisuje naraz wszystkie opcje grupy `feuer` (`feuer_social`, `feuer_formularz_odbiorca`, `feuer_zapis_cena_uprawnienia`, `feuer_zapis_koordynatorka`, `feuer_gus_klucz`, `feuer_organizacja`).
- **[9qrhav]** Opcje nie są wystawione w REST API ustawień (`/wp/v2/settings`).

### Pola

| ID | Pole | Klucz | Typ i wartości | Dozwolone | Wymagane / domyślne | Uwagi |
|---|---|---|---|---|---|---|
| **[rrgwk9]** | Linki social: Facebook, Instagram, YouTube, LinkedIn | `feuer_social` | tablica serwis → adres; klucze `facebook`, `instagram`, `youtube`, `linkedin` | pole adresu (URL) na serwis | domyślnie pusta | stały zestaw serwisów w kodzie, w tej kolejności; brak adresu = ikona niewyświetlana (opis sekcji „Brak linku = ikona niewyświetlana.") |
| **[eaq9jg]** | E-mail odbiorcy formularza | `feuer_formularz_odbiorca` | adres e-mail | pole e-mail | domyślnie pusty | sekcja „Formularz kontaktowy" |
| **[y9awrh]** | Cena uprawnienia SEP | `feuer_zapis_cena_uprawnienia` | kwota w zł netto za wniosek, tekst z kropką (np. `480.60`) | pole liczbowe (krok 0,01), dopisek „zł netto za wniosek" | domyślnie pusta | sekcja „Formularz zapisu na szkolenie"; opis „Wspólna dla wszystkich szkoleń z formularzem „Zapis na szkolenie otwarte z SEP”."; produkcja: `480.60` |
| **[64zdg9]** | E-mail koordynatorki zapisów | `feuer_zapis_koordynatorka` | adres e-mail | pole e-mail | domyślnie pusty | sekcja „Formularz zapisu na szkolenie"; opis „Odbiorca zgłoszeń zapisu; na ten adres klient odpowiada na e-mail potwierdzenia."; produkcja: `kamila.nabialek@feuer.pl` |
| **[wc7zve]** | Klucz GUS | `feuer_gus_klucz` | klucz użytkownika usługi GUS (BIR) | pole tekstowe | domyślnie pusty | sekcja „Formularz zapisu na szkolenie"; opis „Klucz użytkownika usługi GUS (BIR). Bez klucza formularz zapisu nie ma przycisku „Pobierz z GUS" — nazwę firmy i adres klient wpisuje ręcznie."; ze stałą `FEUER_GUS_KLUCZ` (środowiska dev) opis „Na tym środowisku działa klucz testowy ze stałej FEUER_GUS_KLUCZ w wp-config.php (baza testowa GUS) — wartość pola nie jest używana." (integracje.md, [vmt696]); produkcja: klucz zamówiony przez Feuer |
| **[p3qxtw]** | Dane organizacji: Nazwa prawna, NIP, Ulica i numer, Kod pocztowy, Miejscowość, Telefony, E-mail | `feuer_organizacja` | tablica: `nazwa_prawna`, `nip`, `ulica`, `kod`, `miejscowosc`, `telefony`, `email` | tekst jednowierszowy, bez formatów; Telefony — tekst z łamaniem wiersza (3 wiersze, jeden numer w wierszu); E-mail — pole e-mail | domyślnie pusta | sekcja „Dane organizacji"; podpowiedź pod Telefonami „Po jednym w wierszu, z kierunkowym kraju (+48)." — formatu numeru telefonu ani NIP-u nikt nie sprawdza (zapis i wyświetlenie takie, jak wpisane) |

- **[tuzhz6]** Zapis `feuer_social`: wyłącznie klucze czterech serwisów (inne odrzucane); adres przez `esc_url_raw` — bez protokołu dostaje `http://`, z protokołem spoza dozwolonych w WordPressie (np. `javascript:`) staje się pusty; puste wartości usuwane z opcji.
- **[exuqdq]** Zapis `feuer_formularz_odbiorca`: `sanitize_email` — niepoprawny adres zapisuje się jako pusty, bez komunikatu w panelu.
- **[knd5zn]** Zapis `feuer_zapis_cena_uprawnienia`: kwota do 6 cyfr z najwyżej dwoma miejscami po przecinku albo kropce, zapisana z kropką (`feuer_zapis_cena_oczysc()`); inna wartość zapisuje się jako pusta, bez komunikatu. Zapis `feuer_zapis_koordynatorka` — `sanitize_email`, jak odbiorca formularza ([exuqdq]); `feuer_gus_klucz` — `sanitize_text_field`.
- **[wmv3mz]** Zapis `feuer_organizacja`: wyłącznie siedem znanych pól (inne klucze odrzucane); nazwa, NIP, ulica, kod, miejscowość — `sanitize_text_field` (bez HTML, jedna linia); telefony — `sanitize_textarea_field` (bez HTML, wiersze zostają); e-mail — `sanitize_email` (niepoprawny zapisuje się jako pusty, bez ostrzeżenia); pola puste po czyszczeniu nie trafiają do opcji.
- **[r2nvkv]** Sekcja „Formularz kontaktowy" pokazuje stan logu zgłoszeń: brak stałej `FEUER_ZGLOSZENIA_KATALOG` — „Log zgłoszeń wyłączony: brak stałej FEUER_ZGLOSZENIA_KATALOG w wp-config.php."; plik logu czytelny (także pusty) — link „Pobierz log zgłoszeń" (formularz-kontaktu.md, [4fw86a]); stała jest, a pliku brak albo nieczytelny — „Log zgłoszeń jest pusty.".
- **[duq4sh]** Opis sekcji „Dane organizacji": „Dane w stopce serwisu i dla Google (strona główna). Puste pole nie wyświetla się w stopce. Nazwa i logo dla Google — nazwa i ikona witryny (Ustawienia → Ogólne). Adres i telefony są też w sekcji „Dane kontaktu" (Sekcje) — zmiana w obu miejscach."

## Edycja i uprawnienia

- **[3cyzrx]** Stronę Ustawienia → Feuer otwiera i zapisuje wyłącznie administrator (`manage_options`).
- **[r9vfap]** Ustawienia → Feuer administrator czyta i zmienia także z czatu — operacje „Ustawienia serwisu" i „Zmiana ustawień serwisu" (cms-z-czatu.md, „Operacje administratora"): te same pola i to samo czyszczenie wartości (`feuer_social_oczysc()`, `feuer_organizacja_oczysc()`, `feuer_zapis_cena_oczysc()`, `sanitize_email`, `sanitize_text_field`); wartość, którą strona ustawień czyści albo zapisuje jako pustą, operacja odrzuca.

## Odbiorcy

- **[mu2fed]** `feuer_social` — ikony social w stopce i `sameAs` danych strukturalnych `Organization`.
- **[86wby2]** `feuer_formularz_odbiorca` — adres, na który trafiają zgłoszenia z formularza kontaktu; na środowiskach dev zamiast niego — stała `FEUER_ODBIORCA_TESTOWY` (formularz-zapisu.md, [cp8p2q]).
- **[m8rs78]** `feuer_zapis_cena_uprawnienia` — cena wniosku o uprawnienia w panelu zamówienia i koszcie formularza zapisu (wariant „z SEP"); `feuer_zapis_koordynatorka` — adresat zgłoszeń zapisu i `Reply-To` e-maila do klienta, na środowiskach dev zastępowany stałą testową (formularz-zapisu.md, [b6gukq], [cp8p2q]); `feuer_gus_klucz` — klucz zapytań „Pobierz z GUS" i warunek wyświetlenia przycisku w formularzu zapisu, na środowiskach dev zastępowany stałą z kluczem testowym (integracje.md, [vmt696]; formularz-zapisu.md, [ytkpfn]).
- **[vaxsex]** `feuer_organizacja` — dane firmy w stopce ([README bloku `stopka`](blok-stopka.md), „Dane") i dane strukturalne `Organization` na stronie głównej; nazwa prawna, adres, telefony i e-mail — także akapit danych organizacji `/llms.txt` ([seo.md](seo.md), [8rkrdm]).
- **[adw9sx]** Adres i telefony są zapisane także w treści sekcji `dane-kontaktu` (karta Sekcji kontaktowej) — dwa niezależne zapisy; zmiana wymaga edycji w obu miejscach.
