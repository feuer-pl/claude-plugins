# Paleta treści

Bloki treści redakcyjnej (typografia A40) i ich ograniczenia w edytorze. Reguły wspólne bloków i zestawy formatów: [bloki.md](bloki.md); bloki dostępne w edytorze i blokady `theme.json`: [uprawnienia.md](uprawnienia.md).

## Skład

- **[bfkh35]** Lista bloków palety jest w jednym miejscu — `feuer_paleta_tresci()` (`includes/paleta.php`); `core/list-item` i `core/button` wchodzą jako elementy swoich rodziców (lista, przyciski).

| ID | Element | Blok | Ograniczenia |
|---|---|---|---|
| **[bm3dc9]** | Akapit | `core/paragraph` | bez wyrównania i typografii bloku |
| **[2wpbfg]** | Lead | `core/paragraph`, styl „Lead" (`is-style-wstep`) | jak akapit |
| **[8gk4af]** | Ramka wyróżnienia | `core/paragraph`, styl „Wyróżnienie" (`is-style-wyroznienie`) | jak akapit |
| **[8jtmy6]** | Wyróżnienie z linią | `core/paragraph`, styl „Wyróżnienie z linią" (`is-style-wyroznienie-linia`) | jak akapit; pogrubiony początek akapitu — formatowaniem redaktora, styl niczego nie pogrubia |
| **[sugm29]** | Hasło (zdanie końcowe sekcji) | `core/paragraph`, styl „Hasło" (`is-style-haslo`) | jak akapit; zawsze do lewej (bez wyrównania tekstu) |
| **[q2s8np]** | Nagłówek | `core/heading` | poziomy 2–4 (`levelOptions`; w treści etapu Programu 3–4 — README bloku), bez wyrównania i typografii bloku |
| **[gx4snr]** | Lista | `core/list` + `core/list-item` | numer początkowy i kolejność odwrotna dozwolone; bez stylu numeracji (litery, cyfry rzymskie) |
| **[4e2zhn]** | Tabela | `core/table` | naprzemienne wiersze zawsze, bez odmian; sekcja nagłówka dozwolona; bez stopki, podpisu, szerokości komórek i wyrównania kolumn; na mobile przewijana poziomo |
| **[vgjcjm]** | Zdjęcie z podpisem | `core/image` | pełny rozmiar (bez wyboru rozdzielczości); bez wyrównania, linku, powiększenia po kliknięciu, wymiarów, skalowania, proporcji, marginesu i stylów |
| **[zawnfx]** | Cytat blokowy (A40.9) | `core/quote` | bez stylów, bez wyrównania tekstu |
| **[h9mf5c]** | Separator | `core/separator` | bez stylów, bez wyrównania |
| **[f7e8pt]** | Przycisk (A41), link akcji (A43) | `core/buttons` + `core/button` | style: „Czerwony" (domyślny), „Czarny", „Drugorzędny", „Link ze strzałką" (A43); ustawienie „Strzałka"; bez szerokości i zaokrąglenia |
| **[q7ddhc]** | Dwie kolumny | `feuer/dwie-kolumny` | README bloku |
| **[xvmx4u]** | Sprawdź także | `feuer/sprawdz-takze` | README bloku |
| **[3dw525]** | Opinia klienta (K15) | `feuer/cytat` | README bloku |

- **[ekhd7d]** Kod (A40.8) jest poza paletą: blok `core/code` poza listą (strefy treści bloków go nie przyjmują), format inline „kod" wyłączony.
- **[4du539]** Style bloków core palety rejestruje wtyczka (`register_block_style`); napisy stylów i kontrolek — przez i18n ([wielojezycznosc.md](wielojezycznosc.md), [v25q78]).

## Gdzie obowiązuje

- **[8psccg]** Paleta jest listą dozwolonych bloków (`allowedBlocks`) stref treści redakcyjnej bloków `feuer/karta-opisu-produktu-pozycja` (etap Programu), `feuer/tekst-zdjecie`, `feuer/kluczowe-informacje` (wstęp), `feuer/top-kontentowy` (karta) i `feuer/szare-tlo` — nadaje ją filtr `block_type_metadata` (`feuer_paleta_w_blokach()`), `block.json` tych bloków listy nie powtarza; nowy blok ze strefą treści redakcyjnej — dopisanie do listy w filtrze.
- **[7dr2f7]** `feuer/szare-tlo` przyjmuje paletę, ale sam do niej nie należy — strefy treści bloków go nie przyjmują.
- **[p69bw2]** Bloki palety stoją także bezpośrednio w treści stron (`page`) i produktów, między sekcjami — wyglądają jak w treści artykułu, na froncie i w edytorze.
- **[zpunnt]** Pole albo strefa z ograniczoną listą elementów palety (np. odpowiedź FAQ, wartość wiersza Kluczowych informacji) — wygląd elementów zawsze wg atomów treści redakcyjnej (A40).

## Formaty inline

- **[7wwnuc]** Formaty inline w blokach core palety: pogrubienie, kursywa, link, podkreślenie, przekreślenie i kolor marki (`feuer/akcent-marki`, `span.akcent-marki`); kolor marki — poza tekstem przycisku (`core/button`). Bloki core nie zawężają formatów (bez `allowedFormats`).
- **[n55vmn]** Pozostałe formaty core (kod, indeksy, kolor tekstu i podświetlenie, obraz inline, przypisy, klawisz, język) są wyrejestrowane w całym edytorze — także w polach bloków firmowych; formaty spoza `core/` zostają.
- **[ve4jan]** Formatów „Akcent" (`feuer/akcent`, `feuer/tytul-duzy`) nie ma w blokach core — tylko w polach bloków firmowych ([bloki.md](bloki.md), „Zestawy formatów").

## Przycisk

- **[c2qkgn]** Link przycisku dostaje klasy atomu: `przycisk` (A41) i odmianę `przycisk-czarny` / `przycisk-drugorzedny`; styl „Link ze strzałką" — `link-akcji` (A43) zamiast `przycisk`. Front — filtr `render_block_core/button`, edytor — te same klasy (`editor.BlockEdit`); wygląd w całości z `atomy.css` motywu.
- **[ugyumj]** Style przycisku: „Czerwony" i „Czarny" — przycisk wypełniony, „Drugorzędny" — przycisk z obrysem, „Link ze strzałką" — link tekstowy bez tła i obrysu, ze strzałką →; ustawienie „Strzałka" działa we wszystkich stylach.
- **[wre476]** Ustawienie „Strzałka" (panel „Przycisk" w ustawieniach bloku) — we wszystkich stylach, domyślnie włączone; wyłączenie zapisuje atrybut `bezStrzalki: true`; włączone — klasa `przycisk-strzalka`.
- **[9fakc7]** Motyw usuwa z domyślnego `theme.json` rdzenia style elementu `button` i bloku `core/button` (tło, zaokrąglenie, padding — filtr `wp_theme_json_data_default`); przycisk ma wyłącznie wygląd atomu A41.

## Ograniczenia bloków core

- **[bfdgnd]** Ograniczenia bloków core nakłada `includes/paleta.js` (zwykły plik bez buildu), ładowany w każdym edytorze blokowym (`enqueue_block_editor_assets`) bez warunku typu wpisu — obowiązują bloki core wszędzie, nie tylko w strefach palety.
- **[f5tg7j]** Ograniczenia per element — tabela „Skład" (kolumna „Ograniczenia"); „typografia bloku" to wcięcie wiersza i dopasowanie tekstu; style core wyłączone m.in.: „Stripes", „Zaokrąglony", odmiany separatora, „Zwykły", fill / outline.
- **[puve5w]** Kontrolki bez wyłącznika w core: atrybut zerowany przy każdej zmianie (nic nie trafia do treści) i kontrolka ukryta stylem na czas zaznaczenia bloku — obraz: link, powiększenie po kliknięciu, wymiary, skalowanie, proporcje, uchwyty zmiany rozmiaru; tabela: stopka, podpis; cytat blokowy: wyrównanie tekstu; lista: styl numeracji. Szerokość komórek i wyrównanie kolumn tabeli — kontrolki tylko ukryte (atrybuty nie są zerowane; CSS palety je pomija).
- **[uqs87r]** Obraz wstawiany w pełnym rozmiarze (`imageDefaultSize` = `full`, `block_editor_settings_all`), wybór rozdzielczości ukryty; na froncie plik dobiera przeglądarka z `srcset`.
- **[dn7jvj]** Ustawienia stylu bloków core wyłącza `theme.json` motywu ([uprawnienia.md](uprawnienia.md), [uktfp5]).
