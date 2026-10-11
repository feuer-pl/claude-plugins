---
name: cms
description: "Obsługa treści serwisu Feuer.pl przez konektor Feuer CMS — produkty (szkolenia i usługi), terminy szkoleń, kategorie oferty i branże, artykuły Bazy wiedzy, sekcje (np. belka zapowiedzi), strony, bloki, media, SEO, ustawienia serwisu. Użyj przy każdym zleceniu dotyczącym treści serwisu Feuer.pl. Z użytkownikiem rozmawiaj wyłącznie po polsku."
---

# Zachowanie agenta w czacie

## Język

- **[vmy5th]** Agent komunikuje się z użytkownikiem wyłącznie po polsku — niezależnie od języka, w którym użytkownik pisze albo dyktuje.

## Kompletność danych

- **[4puy2z]** Przed zapisem agent sprawdza, czy zlecenie zawiera wszystkie dane wymagane przez operację.
- **[mqpbgv]** O brakujące dane agent pyta użytkownika przed zapisem i uwzględnia odpowiedzi; brakujących wartości nie wymyśla.
- **[su5pbj]** Gdy operacja odpowie listą brakujących i błędnych danych, agent pyta o nie użytkownika i po odpowiedzi ponawia operację.

## Operacje

- **[tmcqsk]** Treść serwisu agent odczytuje i zmienia wyłącznie operacjami konektora. Gdy potrzebnej operacji nie ma, mówi o tym od razu i nie szuka innej drogi — REST, strony publicznej ani plików.
- **[rhab87]** W operacji zapisu agent podaje treść zlecenia (pole `zlecenie`): o co poprosił użytkownik, jego słowami.
- **[kgdtr6]** Zlecenie, którego nie da się wykonać — nie ma pasującej operacji albo konto nie ma uprawnień — agent zapisuje operacją „Zlecenie niewykonane": treść zlecenia słowami użytkownika i powód.

## Podpowiadanie operacji

- **[ukucsm]** Agent podaje użytkownikowi, jakie operacje są dla niego dostępne — w granicach uprawnień zalogowanego konta — w dwóch sytuacjach: gdy użytkownik o to pyta oraz gdy zlecenia nie da się wykonać (nie ma takiej operacji albo konto nie ma uprawnień) — wtedy zamiast samej odmowy podaje, co jest dostępne.
- **[3wyar5]** Listę operacji dostępnych dla konta agent bierze z operacji „Konto" — lista narzędzi konektora nie zależy od uprawnień konta.
- **[66maq3]** Bez pytania użytkownika i bez odmowy agent listy operacji nie wypisuje.

## Odpowiedzi

- **[pfpf7z]** Wpis agent pokazuje tabelą pól: nazwy pól z dokumentu obiektu (np. „Opis na karcie"), nie klucze; wartości ze słownika — nazwami (np. „Webinar otwarty"), nie kodami; tak / nie — słowami; taksonomie produktu — w tej samej tabeli.
- **[mxc3x5]** Pola puste agent wymienia jednym wierszem pod tabelą, bez osobnych wierszy tabeli.
- **[ge5vf9]** Każdy wpis, term i plik, o którym mowa w odpowiedzi — także wpis, którego dotyczy zlecenie, każda pozycja listy i każde odniesienie w polu (powiązany produkt, powiązany artykuł, autor artykułu, obrazek) — agent podaje tytułem albo nazwą z linkiem z odpowiedzi operacji: do strony (`adres`), a gdy strony nie ma (np. sekcja, ekspert, grupa) — do edycji w panelu (`edycja`). Nigdy samym ID; bez linku zostaje wyłącznie obiekt, dla którego operacja nie zwraca żadnego.

## Wersja pluginu

- **[jd752s]** Na pytanie o wersję pluginu agent podaje dane zapisane w skillu („Dane wersji"): numer wersji pluginu i commit dokumentacji, z której zbudowano skill — np. „Plugin feuer-dev 0.1.3, dokumentacja z commita 70985da".

## Dokumentacja

- **[uhteek]** Działanie serwisu agent zna z dokumentów skilla: przed operacją otwiera dokument obiektu, którego dotyczy zlecenie, a przy treści blokowej — także README użytych bloków ([bloki.md](references/bloki.md), „Rejestr").

## Dane wersji

Plugin feuer-dev 0.1.4, dokumentacja z commita ca22af7.

## Spis dokumentów

- [model-tresci.md](references/model-tresci.md) — Model treści: Zakres, Typy wpisów, Taksonomie, Relacje, Wspólne
- [produkt.md](references/produkt.md) — Produkt: Typ wpisu, Pola, Relacje, Edycja i uprawnienia, Odbiorcy, Wielojęzyczność
- [taksonomie.md](references/taksonomie.md) — Taksonomie: Wspólne, Oferta (`oferta`), Branża (`branza`), Grupa produktów (`grupa`), Oznaczenia (`oznaczenie`)
- [artykuly.md](references/artykuly.md) — Artykuły: Artykuł (`post`), Ekspert (`ekspert`), Wielojęzyczność
- [sekcje.md](references/sekcje.md) — Sekcje: Typ wpisu, Zestaw sekcji, Sekcje kategorii i branż, Edycja i uprawnienia, Wielojęzyczność
- [ustawienia.md](references/ustawienia.md) — Ustawienia: Ustawienia → Feuer, Edycja i uprawnienia, Odbiorcy
- [media.md](references/media.md) — Media: Biblioteka mediów, Filmy, Obrazy, Edycja i uprawnienia, Wielojęzyczność
- [uprawnienia.md](references/uprawnienia.md) — Uprawnienia: Blokady edycji, Bloki w edytorze, Site Editor
- [bloki.md](references/bloki.md) — Bloki: Typy bloków, Model edycji, Zestawy formatów, Linki i pola panelu, Źródła pozycji, Film zamiast zdjęcia, Zakładki i akordeon, Karuzele, Elementy wspólne, Kod QR, Rejestr
- [paleta-tresci.md](references/paleta-tresci.md) — Paleta treści: Skład, Gdzie obowiązuje, Formaty inline, Przycisk, Ograniczenia bloków core
- [wzorce-stron.md](references/wzorce-stron.md) — Wzorce stron: Rejestracja, Strona główna, Strona kontentowa, Strona produktu
- [seo.md](references/seo.md) — SEO: Mechanizm, Pola nadpisania, Title, Meta description, OG / Twitter, Canonical, hreflang, Indeksowanie, Sitemapa, Dane strukturalne
- [strony.md](references/strony.md) — Strony: Typy stron i szablony, Rama strony, Adresy, Strona 404, Strona błędu serwera, Ikona witryny, Typy stron pominięte
- [nawigacja.md](references/nawigacja.md) — Nawigacja: Header i menu, Elementy rozwijane, Okruszki i link wstecz, Strona lądowania
- [strony-zbiorcze.md](references/strony-zbiorcze.md) — Strony zbiorcze: Strony, Karta produktu, Grupa produktów, Widoczność i kolejność, Strona „Oferta", Strona kategorii, Strona branży, Strony filarów, Wyszukiwarka katalogu
- [baza-wiedzy.md](references/baza-wiedzy.md) — Baza wiedzy: Strona Bazy wiedzy, Lista artykułów, Wyszukiwarka listy, Strona artykułu, Link i CTA produktu artykułu, Spis treści
- [wielojezycznosc.md](references/wielojezycznosc.md) — Wielojęzyczność: Stan, Mechanizm, Języki i adresy, Zakres tłumaczeń, Abstrakcja tłumaczeń, Przełącznik języka, Zasady redakcyjne, I18n
