---
name: cms
description: "Obsługa treści serwisu Feuer.pl przez konektor Feuer CMS — produkty (szkolenia i usługi), terminy szkoleń, kategorie oferty i branże, artykuły Bazy wiedzy, sekcje (np. belka zapowiedzi), strony, bloki, media, SEO, ustawienia serwisu. Użyj przy każdym zleceniu dotyczącym treści serwisu Feuer.pl."
---

# Zachowanie agenta w czacie

## Język

- **[vmy5th]** Agent komunikuje się z użytkownikiem wyłącznie po polsku — niezależnie od języka, w którym użytkownik pisze albo dyktuje.

## Kompletność danych

- **[4puy2z]** Przed zapisem agent sprawdza, czy zlecenie zawiera wszystkie dane wymagane przez operację.
- **[mqpbgv]** O brakujące dane agent pyta użytkownika przed zapisem i uwzględnia odpowiedzi; brakujących wartości nie wymyśla.

## Podpowiadanie operacji

- **[ukucsm]** Agent podaje użytkownikowi, jakie operacje są dla niego dostępne — w granicach uprawnień zalogowanego konta — w dwóch sytuacjach: gdy użytkownik o to pyta oraz gdy zlecenia nie da się wykonać (nie ma takiej operacji albo konto nie ma uprawnień) — wtedy zamiast samej odmowy podaje, co jest dostępne.
- **[66maq3]** Bez pytania użytkownika i bez odmowy agent listy operacji nie wypisuje.

## Dokumentacja

- **[uhteek]** Działanie serwisu agent zna z dokumentów skilla: przed operacją otwiera dokument obiektu, którego dotyczy zlecenie, a przy treści blokowej — także README użytych bloków ([bloki.md](references/bloki.md), „Rejestr").

## Spis dokumentów

### Model treści

- [model-tresci.md](references/model-tresci.md) — przegląd: typy wpisów, taksonomie, relacje między obiektami, reguły wspólne (komentarze, rewizje, treść w bazie).
- [produkt.md](references/produkt.md) — typ `produkt` (szkolenia i usługi): pola i słowniki, metaboks „Dane produktu", odbiorcy pól, synchronizacja tłumaczeń.
- [taksonomie.md](references/taksonomie.md) — `oferta`, `branza`, `grupa`, `oznaczenie`: pola termów, kolejność, słownik oznaczeń, blokady.
- [artykuly.md](references/artykuly.md) — artykuły Bazy wiedzy (`post`) i eksperci: pola, flaga list, produkt artykułu.
- [sekcje.md](references/sekcje.md) — typ `sekcja`: zestaw sekcji, tworzenie automatyczne, ochrona, blokada struktury, odczyt po slugu.
- [ustawienia.md](references/ustawienia.md) — Ustawienia → Feuer (linki social, odbiorca formularza, dane organizacji) i wykorzystywane ustawienia WordPressa.
- [media.md](references/media.md) — zdjęcia i filmy: biblioteka mediów, wgranie filmu (plakat, faststart), miniatury AVIF, ładowanie na stronie.

### Uprawnienia

- [uprawnienia.md](references/uprawnienia.md) — role i konta, blokady edycji, bloki w edytorze, Site Editor, dane kont, REST bez logowania.

### Bloki

- [bloki.md](references/bloki.md) — typy bloków, reguły wspólne modelu edycji (teksty, pola obowiązkowe, limity, pozycje, zachowania w edytorze), zestawy formatów, linki i pola panelu, źródła pozycji, film zamiast zdjęcia, zakładki, karuzele, kod QR, dane i kontekst bloków, bloki ramy i szablonowe, elementy wspólne, rejestr bloków z linkami do README.
- [paleta-tresci.md](references/paleta-tresci.md) — paleta treści redakcyjnej: skład, strefy treści, formaty inline, przycisk, ograniczenia bloków core w edytorze.
- [wzorce-stron.md](references/wzorce-stron.md) — wzorce stron (strona główna, strona kontentowa, Szkolenie, Usługa) i mapowanie pięter szablonu treści produktu na bloki.

### Strony

- [strony.md](references/strony.md) — typy stron i szablony motywu, rama strony, adresy, strona 404, strona błędu serwera, ikona witryny, typy stron pominięte.
- [nawigacja.md](references/nawigacja.md) — header i menu (drzewo oferty, cache), elementy rozwijane, okruszki i link wstecz, strona lądowania.
- [strony-zbiorcze.md](references/strony-zbiorcze.md) — „Oferta", strony kategorii i branży, strony filarów: karta produktu, grupa, widoczność i kolejność, wyszukiwarka katalogu.
- [baza-wiedzy.md](references/baza-wiedzy.md) — strona Bazy wiedzy, lista artykułów, wyszukiwarka listy, strona artykułu, link i CTA produktu artykułu, spis treści.

### Wielojęzyczność

- [wielojezycznosc.md](references/wielojezycznosc.md) — Polylang Free: stan wdrożenia, języki i adresy, zakres tłumaczeń, abstrakcja tłumaczeń, przełącznik języka, zasady redakcyjne, i18n.

### SEO i migracja

- [seo.md](references/seo.md) — metadane stron: pola nadpisania, title, meta description, OG / Twitter, canonical, hreflang, indeksowanie, sitemapa, dane strukturalne.
