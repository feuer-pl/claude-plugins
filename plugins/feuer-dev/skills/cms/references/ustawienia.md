# Ustawienia

Globalne ustawienia serwisu: strona Ustawienia → Feuer (linki social, odbiorca formularza kontaktu, dane organizacji) i wykorzystywane ustawienia WordPressa. Przegląd modelu: [model-tresci.md](model-tresci.md).

## Ustawienia → Feuer

- **[wn44bs]** Strona ustawień serwisu — Ustawienia → Feuer (slug `feuer`, nagłówek „Ustawienia serwisu Feuer"), na natywnym API ustawień WordPressa; sekcje w kolejności: „Linki social", „Formularz kontaktowy", „Dane organizacji".
- **[qa44d9]** Ustawienia to jeden zestaw dla wszystkich języków — zwykłe opcje WordPressa, bez wersji per język.
- **[r7deg8]** Wszystkie sekcje są jednym formularzem z jednym przyciskiem zapisu: zapisuje naraz wszystkie opcje grupy `feuer` (`feuer_social`, `feuer_formularz_odbiorca`, `feuer_organizacja`).
- **[9qrhav]** Opcje nie są wystawione w REST API ustawień (`/wp/v2/settings`).

### Pola

| ID | Pole | Klucz | Typ i wartości | Dozwolone | Wymagane / domyślne | Uwagi |
|---|---|---|---|---|---|---|
| **[rrgwk9]** | Linki social: Facebook, Instagram, YouTube, LinkedIn | `feuer_social` | tablica serwis → adres; klucze `facebook`, `instagram`, `youtube`, `linkedin` | pole adresu (URL) na serwis | domyślnie pusta | stały zestaw serwisów w kodzie, w tej kolejności; brak adresu = ikona niewyświetlana (opis sekcji „Brak linku = ikona niewyświetlana.") |
| **[eaq9jg]** | E-mail odbiorcy formularza | `feuer_formularz_odbiorca` | adres e-mail | pole e-mail | domyślnie pusty | sekcja „Formularz kontaktowy" |
| **[p3qxtw]** | Dane organizacji: Nazwa prawna, Ulica i numer, Kod pocztowy, Miejscowość, Telefony, E-mail | `feuer_organizacja` | tablica: `nazwa_prawna`, `ulica`, `kod`, `miejscowosc`, `telefony`, `email` | tekst jednowierszowy, bez formatów; Telefony — tekst z łamaniem wiersza (3 wiersze, jeden numer w wierszu); E-mail — pole e-mail | domyślnie pusta | sekcja „Dane organizacji"; podpowiedź pod Telefonami „Po jednym w wierszu, z kierunkowym kraju (+48)." — formatu numeru nikt nie sprawdza |

- **[tuzhz6]** Zapis `feuer_social`: wyłącznie klucze czterech serwisów (inne odrzucane); adres przez `esc_url_raw` — bez protokołu dostaje `http://`, z protokołem spoza dozwolonych w WordPressie (np. `javascript:`) staje się pusty; puste wartości usuwane z opcji.
- **[exuqdq]** Zapis `feuer_formularz_odbiorca`: `sanitize_email` — niepoprawny adres zapisuje się jako pusty, bez komunikatu w panelu.
- **[wmv3mz]** Zapis `feuer_organizacja`: wyłącznie sześć znanych pól (inne klucze odrzucane); nazwa, ulica, kod, miejscowość — `sanitize_text_field` (bez HTML, jedna linia); telefony — `sanitize_textarea_field` (bez HTML, wiersze zostają); e-mail — `sanitize_email` (niepoprawny zapisuje się jako pusty, bez ostrzeżenia); pola puste po czyszczeniu nie trafiają do opcji.
- **[r2nvkv]** Sekcja „Formularz kontaktowy" pokazuje stan logu zgłoszeń: brak stałej `FEUER_ZGLOSZENIA_KATALOG` — „Log zgłoszeń wyłączony: brak stałej FEUER_ZGLOSZENIA_KATALOG w wp-config.php."; plik logu czytelny (także pusty) — link „Pobierz log zgłoszeń" (formularz-kontaktu.md, [4fw86a]); stała jest, a pliku brak albo nieczytelny — „Log zgłoszeń jest pusty.".
- **[duq4sh]** Opis sekcji „Dane organizacji": „Dane dla Google (strona główna). Nazwa — nazwa witryny, logo — ikona witryny (Ustawienia → Ogólne). Adres i telefony są też w sekcji kontaktowej „O firmie" — zmiana w obu miejscach."

## Edycja i uprawnienia

- **[3cyzrx]** Stronę Ustawienia → Feuer otwiera i zapisuje wyłącznie administrator (`manage_options`).

## Odbiorcy

- **[mu2fed]** `feuer_social` — ikony social w stopce i `sameAs` danych strukturalnych `Organization`.
- **[86wby2]** `feuer_formularz_odbiorca` — adres, na który trafiają zgłoszenia z formularza kontaktu.
- **[vaxsex]** `feuer_organizacja` — dane strukturalne `Organization` na stronie głównej.
- **[adw9sx]** Adres i telefony są zapisane także w treści sekcji `dane-kontaktu` (karta Sekcji kontaktowej) — dwa niezależne zapisy; zmiana wymaga edycji w obu miejscach.
