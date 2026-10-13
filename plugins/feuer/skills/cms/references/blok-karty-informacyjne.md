# feuer/karty-informacyjne

„Karty informacyjne na zdjęciu" — pas ze zdjęciem albo filmem (osobne kreacje desktop i mobile) z tekstem i karuzela 1–10 kart ([feuer/karty-informacyjne-karta](blok-karty-informacyjne-karta.md)); odmiana hero — hero strony głównej. Typ: T ([bloki.md](bloki.md), „Typy bloków"). Film: [bloki.md](bloki.md), „Film zamiast zdjęcia"; karuzela: [bloki.md](bloki.md), „Karuzele".

## Gdzie

- **[srwdrq]** Samodzielna sekcja pełnej szerokości w treści stron i produktów, poza paletą treści redakcyjnej; na stronie wielokrotnie, z różnymi nagłówkami (np. „Dlaczego Feuer?", „Co zyskujesz?") — nagłówek jest polem bloku, nie zaszytą etykietą.
- **[bh63eh]** Hero strony głównej to odmiana tego bloku (atrybut `hero`), nie osobny blok; jedna na stronę, zawsze z kartami. Miejsca osadzenia hero kod nie wymusza.

## Pola

| ID | Pole | Atrybut | Rodzaj | Dozwolone | Limit | Wymagane / domyślne |
|---|---|---|---|---|---|---|
| **[3zwc8q]** | Odmiana hero | `hero` | przełącznik „Odmiana hero" (panel „Ustawienia"); zablokowany, gdy inny blok na stronie ma już hero (opis: „Na stronie jest już blok w odmianie hero — dozwolony jeden.") | — | jeden hero na stronę | wyłączone |
| **[gntprn]** | Podświetlenie karty z linkiem (hover) — tylko hero | `podswietlenie` | wybór w panelu „Ustawienia" | „Zwykłe — tytuł czerwony", „Czerwone" (cała karta czerwona, tekst biały) | — | zwykłe |
| **[26zbbw]** | Proporcja pasa (desktop) | `pas` | wybór w panelu „Ustawienia" | 2,9:1 (`2-9`), 21:9, 16:9; mobile — stała | — | 2,9:1 |
| **[freqmj]** | Medium | `medium` | wybór w panelu „Ustawienia": „Zdjęcie", „Film MP4 (pętla bez dźwięku)"; zmiana nie kasuje kreacji drugiego medium (osobne atrybuty) | zdjęcie, film | — | zdjęcie |
| **[862sv4]** | Kreacje pasa: desktop i mobile (osobna kreacja, bez przycinania desktopowej) | `zdjecie` + `zdjecieMobile` albo `film` + `filmMobile` (ID) | medium — toolbar bloku | zdjęcie: obrazy; film: wyłącznie `video/mp4` | — | obie obowiązkowe; brak kreacji mobile wybranego medium (niewybrana, usunięta albo złego typu — także w świeżym bloku) blokuje zapis i autozapis wpisu |
| **[w36ke4]** | Tekst na pasie | `napis` — lista linii `{ tekst, lead }` | jedno pole wieloliniowe: każda linia osobnym polem bez miękkich łamań; styl linii w toolbarze — „Linia główna" / „Lead" | „Akcent w nagłówkach" ([bloki.md](bloki.md), [s56shy]); w hero `span.akcent` = słowo większe | — | opcjonalne — domyślnie jedna pusta linia; puste (wszystkie linie bez tekstu): bez nagłówka i leadu |
| **[m2htay]** | Karty | bloki wewnętrzne | `feuer/karty-informacyjne-karta`, przestawiane dowolnie (`templateLock: false`) | wyłącznie `feuer/karty-informacyjne-karta` | 1–10 | min. 1 — nowy blok ma jedną kartę, po usunięciu ostatniej pojawia się pusta (bez wpisu w historii zmian) |

- **[3vfxxy]** Bez ostrzeżenia o rozmiarze filmu — blok sprawdza wyłącznie typ pliku.

## Warianty

- **[p4uqab]** Hero: linia główna tekstu to `h1` (zwykła odmiana — `h2`), tekst większy; karty mogą mieć link (kontekst `feuer/hero` dla kart). Poza hero karty są prezentacyjne: nieklikalne, bez hovera i efektu naciśnięcia; karta z linkiem w hero — hover wg „Podświetlenia". Wariantu K25 (karta = zakładka z panelem) w bloku nie ma.
- **[kc832y]** Hero jako pierwszy blok treści strony głównej (header w wariancie `data-przewijanie="glowna"`) podjeżdża pod miejsce headera: pas rośnie o wysokość headera, nagłówek pasa schodzi o tę wysokość, header leży na nim jako półprzezroczysta maska (header stoi w części szablonu poza `<main>`).

## Dane

- **[n5htn2]** Pas: jedno zdjęcie albo film (tło nie jest karuzelą); przewija się wyłącznie rząd kart — na froncie zawsze karuzela, bez autoplay.
- **[xv4wna]** Obie kreacje poprawne: zdjęcie jako `picture` z `source` mobile do 639 px (rozmiar `full`, `sizes="100vw"`, mobile z własnym `srcset`), film przez `feuer_film()`. Brak którejś kreacji: osobne warstwy desktop i mobile (`karty-informacyjne-medium-desktop` / `-mobile`), w miejscu brakującej obraz zastępczy; przy medium „film" brakujący film nie wraca do zdjęcia. Zdjęcia pasa dekoracyjne (alt pusty); w odmianie hero `loading="eager"` i `fetchpriority="high"`, poza hero `loading="lazy"` ([media.md](media.md), [s4ae2p], [tewya3]).
- **[6re8xe]** Tekst na pasie: linie główne — jeden nagłówek (`h2`, w hero `h1`) z liniami przez `<br>`, linie leadu — jeden `p.karty-informacyjne-lead` pod nim, niezależnie od kolejności linii w polu. Puste linie zostają i przesuwają tekst w pionie (redaktor reguluje położenie pustymi liniami); pusta linia na końcu grupy dostaje dodatkowe `<br>`.
- **[z3xgby]** Karty zapisane jako bloki wewnętrzne (`save` = `InnerBlocks.Content`), front renderuje blok po stronie serwera.

## Edytor

- **[sx8728]** Tekst na pasie: Enter dzieli linię w miejscu kursora (ten sam styl), Backspace na początku i Delete na końcu linii scalają ją z sąsiednią; przyciski stylu widać tylko przy aktywnej linii; lead zawsze pod liniami głównymi — ustawienie leadu obejmuje linię bieżącą i niższe, linii głównej — bieżącą i wyższe.
- **[vgh6qz]** Brak kreacji mobile — komunikat w bloku „Brak zdjęcia mobile — wpisu nie można zapisać. Wybierz „Zdjęcie mobile" w pasku narzędzi bloku." (dla filmu: „Brak filmu mobile — …"); blokada zapisu zdejmowana po uzupełnieniu (pułapka `lockPostSaving`: [bloki.md](bloki.md), [adddkf]).
- **[hbbacy]** Pas pokazuje obie warstwy (desktop i mobile), przełączane szerokością kanwy; film gra automatycznie, bez dźwięku, w pętli; w miejscu brakującej kreacji obraz zastępczy.
- **[v54xka]** Rząd kart zawijany, wszystkie karty widoczne; kartę dodaje podpisany przycisk „Dodaj kartę" (drugorzędny, z ikoną plus) na końcu rzędu, widoczny przy mniej niż 10 kartach — domyślny „+" w rogu bloku nachodziłby na kartę.

## Przykład

```html
<!-- wp:feuer/karty-informacyjne {"zdjecie":58,"zdjecieMobile":59,"napis":[{"tekst":"Dlaczego Feuer?","lead":false}]} -->
<!-- wp:feuer/karty-informacyjne-karta {"tytul":"16 lat<br>na rynku pracy","tekst":"Obsługujemy firmy polskie i zagraniczne od 2010 roku."} /-->
<!-- wp:feuer/karty-informacyjne-karta {"tytul":"Obsługa po polsku i angielsku","tekst":"Dokumentacja, szkolenia i codzienna komunikacja w języku, w którym pracujecie."} /-->
<!-- /wp:feuer/karty-informacyjne -->

<!-- wp:feuer/karty-informacyjne {"hero":true,"pas":"21-9","medium":"film","film":60,"filmMobile":61,"napis":[{"tekst":"Przeprowadzimy Cię","lead":false},{"tekst":"\u003cspan class=\u0022akcent\u0022\u003ebezpiecznie\u003c/span\u003e przez system BHP","lead":false},{"tekst":"Pozytywne skutki wdrożenia standardów BHP z Feuer dla Twojej firmy","lead":true}]} -->
<!-- wp:feuer/karty-informacyjne-karta {"tytul":"97% skuteczność w kontrolach PIP","tekst":"Nasi klienci przechodzą audyty bez problemu."} /-->
<!-- /wp:feuer/karty-informacyjne -->
```
