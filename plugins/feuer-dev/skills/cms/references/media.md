# Media

Zdjęcia i filmy: biblioteka mediów, pliki filmów, wgranie (limit, plakat, przepakowanie, duży film), formaty miniatur, profil kolorów, ładowanie na stronie. Przegląd modelu: [model-tresci.md](model-tresci.md).

## Biblioteka mediów

- Treść, w tym media — przepływ między środowiskami: infrastruktura.md, [q9w3dq].
- Przepływ mediów między środowiskami (produkcja → serwer dev, lokalne) — pomysł: pomysly.md.
- **[pqn7cq]** Media to załączniki WordPressa (`attachment`, w REST `media`), w katalogach `uploads/RRRR/MM/` (opcje domyślne WordPressa).
- **[sd8bgf]** Strony załączników są wyłączone (`wp_attachment_pages_enabled` = 0): adres załącznika (np. `/?attachment_id=N`) przekierowuje 301 na plik w `uploads`.
- **[ma2hnq]** Rozmiary obrazów — domyślne WordPressa (miniatura 150×150 z kadrowaniem, średni 300×300, `medium_large` 768, duży 1024×1024, 1536×1536, 2048×2048; próg dużego oryginału 2560 px); serwis nie rejestruje własnych rozmiarów, bloki używają rozmiaru `full` z `srcset`; wyjątki: zdjęcie autora artykułu i zdjęcia branż w menu — `thumbnail`, certyfikaty w stopce — `medium` (bez `srcset`).
- **[k79y36]** Bloki firmowe wskazują obraz po ID załącznika — ich treść nie zawiera adresów plików; blok `core/image` z palety treści zapisuje w treści adres pliku.
- **[svevbh]** Wspólne zdjęcia stron produktów (pasy Kart informacyjnych z kreacją mobile, belki informacyjne, ikony kroków Procesu współpracy) to jeden zestaw załączników dla wszystkich produktów, oznaczony meta `_feuer_zaslepka` (pas „Co zyskujesz…" — osobne załączniki z kluczem `…#zyskujesz`). Podmiana pliku załącznika zmienia zdjęcie na wszystkich stronach produktów.

## Filmy

### Pliki

- **[2mbp3h]** Film: MP4 H.264, bez ścieżki dźwięku, `moov` przed `mdat` (faststart) — odtwarzanie startuje po pobraniu początku pliku, bez czekania na całość (obsługa `Range`: nginx.md, [qkgn5y]).
- **[m6wsz3]** Osobne pliki desktop i mobile; próg i wybór pliku mobile — [bloki.md](bloki.md), [2x6csc].
- **[e85h5c]** Filmów w bibliotece nie rekompresuje się — dalsze zmniejszanie psuje obraz (treść — falująca woda — słabo się kompresuje).

### Wgranie

- **[egukhf]** Każda droga wgrania MP4 (wp-admin, REST API, WP-CLI) przechodzi przez jeden hak — filtr `wp_read_video_metadata` przy generowaniu metadanych załącznika, wyłącznie dla formatu `mp4`; inne formaty wideo bez zmian.
- **[257t2f]** Limit wgrania pliku przez wp-admin, REST API i formularz z czatu wyznacza PHP (serwer.md, [uhxgnx]) — serwer dev i lokalna instancja dev: 64 MB, produkcja: 2 MB — dla każdej roli i każdego typu pliku; większy plik wgrywa administrator przez WP-CLI (`wp media import` — limit PHP-FPM dotyczy wyłącznie żądań HTTP).
- **[c6wdu4]** Film cięższy niż 5 MB zostaje w bibliotece mediów z ostrzeżeniem „Film jest duży (<rozmiar>) i wymaga przygotowania — skontaktuj się z administratorem.": w panelu — stan obok tytułu na liście biblioteki mediów i wiersz „Uwaga" w szczegółach załącznika, niezależnie od drogi wgrania; w czacie — ostrzeżenie w wyniku operacji mediów (cms-z-czatu.md, „Operacje mediów"). Wgrania ostrzeżenie nie blokuje.
- **[gcvqur]** Plik z `moov` za `mdat` jest przepakowywany bez rekompresji, ze wszystkimi ścieżkami (`ffmpeg -map 0 -c copy -movflags +faststart`), podmienia oryginał, rozmiar w metadanych odświeżony; jakość i rozmiar bez zmian. Błąd przepakowania — plik bez zmian.
- **[my9z2h]** Plakat = pierwsza klatka filmu (0 s) wycięta ffmpeg jako JPEG najwyższej jakości (`-frames:v 1 -q:v 2`) i zapisana jako okładka WordPressa — obrazek wyróżniający załącznika filmu (`attachment:video` z obsługą `thumbnail`). Każdy plik (desktop i mobile) ma plakat z własnej pierwszej klatki, nigdy ze zdjęcia bloku.
- **[mhqmdf]** Rdzeń WordPressa deduplikuje okładki po md5 obrazu — filmy z identyczną pierwszą klatką dzielą jeden załącznik plakatu.
- **[n3aqsm]** Ramka „Obrazek wyróżniający" na ekranie załącznika jest usunięta — plakatu nie zmienia się ręcznie.
- **[jn89jy]** Brak ffmpeg, wyłączone `exec` albo błąd ffmpeg: film bez zmian i bez plakatu, wgranie bez błędu.
- **[bt2mvb]** Pliki tymczasowe wgrania (`<plik>.faststart.mp4` obok filmu, klatka `plakat*` w katalogu tymczasowym) są zawsze usuwane.
- **[wggp4b]** `wp feuer plakaty` — dla filmów wgranych przed wdrożeniem mechanizmu: generuje ponownie metadane każdego załącznika `video/mp4` bez plakatu (tym samym filtrem — przy okazji przepakowanie faststart); film z plakatem albo bez pliku na dysku pominięty z przyczyną w logu („ma plakat", „brak pliku"); dla przetworzonego filmu log z ID plakatu albo „bez plakatu (brak ffmpeg?)".

### Ładowanie na stronie

- **[jjfy82]** Ładowanie filmu na stronie (plik desktop i mobile, plakat, pierwszy ekran i poniżej) — [bloki.md](bloki.md), „Film zamiast zdjęcia", [2x6csc], [qv34eu], [wmk54b].

## Obrazy

- **[9egzb6]** Miniatury (rozmiary pośrednie z JPEG i PNG) zapisywane jako AVIF z jakością 60 (`image_editor_output_format`, `wp_editor_set_quality`); bez obsługi AVIF w PHP serwera — WebP; jakość innych formatów domyślna. Przy jakości 82 część zdjęć byłaby cięższa niż JPEG.
- **[98atba]** Miniatury AVIF obsługuje ok. 95% przeglądarek (Chrome, Firefox, Edge 121+, Safari 16+); starsze miniatur nie pokażą.
- **[6a6sjy]** Pełny rozmiar zostaje oryginałem JPEG / PNG, bez rekompresji: filtr formatu nic nie mapuje, gdy pyta `wp_create_image_subsizes()` (rozpoznanie po stosie wywołań) — WordPress 6.7+ konwertowałby pełny rozmiar razem z miniaturami. Wyjątek: oryginał przeliczany do sRGB ([vptpex]).
- **[7yy3ks]** Oryginał jest `src` obrazu, więc trafia do `srcset` (także szerszy niż 2048 px) — na ekranie o dużej gęstości pikseli przeglądarka może go wybrać. Oryginał powyżej 2560 px: pełnym rozmiarem jest kopia `-scaled` (rozmiar pośredni, więc AVIF).
- **[mk8tgf]** Zmiana formatu lub jakości miniatur obejmuje obrazy już wgrane wyłącznie po `wp media regenerate --skip-delete` (stare kopie zostają na dysku); potem ręczne czyszczenie cache stron.
- **[5j89y2]** Obraz zastępczy artykułu — plik motywu poza biblioteką mediów ([artykuly.md](artykuly.md)).
- **[s4ae2p]** Zdjęcie pierwszego ekranu (element LCP) ma `loading="eager"` i `fetchpriority="high"`; które bloki — README bloku.
- **[tewya3]** Obrazy poniżej pierwszego ekranu mają jawne `loading="lazy"` (WordPress zostawia pierwsze 3 obrazy treści bez `lazy`); obrazy bez atrybutu `loading` (heurystyka WordPressa) i przypisanie do bloków — README bloku.
- **[vptpex]** Zdjęcie z osadzonym profilem kolorów innym niż sRGB (np. Display P3) serwer przelicza do sRGB — każda droga wgrania (wp-admin, REST API, WP-CLI, formularz z czatu), w plikach, które pokazują strony: obrazy pochodne (kopia `-scaled`, miniatury, wynik edycji obrazu w panelu) — przy zapisie przez edytor obrazów serwisu (`Feuer_Edytor_Obrazu`, pierwszy na liście `wp_image_editors`); oryginał — przy wgraniu, gdy zostaje plikiem pełnego rozmiaru (PNG albo obraz nie większy niż 2560 px; JPEG, PNG, WebP i AVIF), zapisany ponownie w swoim formacie i z jakością pliku źródłowego. Oryginał powyżej 2560 px zostaje w swoim profilu — strony go nie pokazują ([7yy3ks]). Przeliczony plik ma osadzony profil sRGB. Obraz bez profilu albo z profilem sRGB (rozpoznanie po nazwie profilu) — bez zmian. Bez Imagick albo przy błędzie przeliczenia — plik bez zmian, wgranie bez błędu.
- **[gfvzrc]** Wgranie obrazu (JPEG, PNG, WebP, AVIF) podnosi limit czasu żądania PHP do 120 s (`set_time_limit()`): przygotowanie dużego zdjęcia — kopia `-scaled`, miniatury AVIF, przeliczenie profilu — trwa na serwerze dłużej niż domyślne 30 s (serwer.md, [8447y9]). Po 60 s nginx kończy żądanie błędem 504 (domyślny limit odczytu odpowiedzi PHP-FPM), a PHP dokańcza przygotowanie pliku.

## Edycja i uprawnienia

- **[qp97xm]** Pliki SVG (np. ikony termów) wgrywa każdy z prawem wgrywania plików (wtyczka Safe SVG, `safe_svg_upload_roles` nieustawione); Safe SVG czyści plik ze skryptów przy wgraniu.

## Wielojęzyczność

- **[mza4r8]** Media nie są tłumaczone (Polylang bez obsługi mediów) — jeden załącznik dla wszystkich języków.
