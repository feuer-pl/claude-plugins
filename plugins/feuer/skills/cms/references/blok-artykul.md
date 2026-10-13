# feuer/artykul

„Artykuł" — cała strona artykułu (`<main>`) z danych bieżącego wpisu w szablonie motywu `single.html`; skrypt edytora bloku rejestruje panele wpisu „Autor artykułu" i „Widoczność na listach". Typ: szablonowy ([bloki.md](bloki.md), „Typy bloków"). Strona artykułu, link i CTA produktu, spis treści: [baza-wiedzy.md](baza-wiedzy.md); pola artykułu i produkt artykułu: [artykuly.md](artykuly.md).

## Gdzie

- **[t9yka4]** Wyłącznie szablon `single.html`: bez atrybutów, poza wstawiaczem ([bloki.md](bloki.md), [89q53x]), bez zapisu jako blok wielokrotnego użytku ([bloki.md](bloki.md), [ecp7bd]).

## Dane

- **[dwx2y9]** Render z bieżącego wpisu (bez wpisu — nic); treść wpisu przez filtr `the_content` do `.tresc` w karcie artykułu.
- **[ufebe3]** Sekcja wstępu (lead i spis treści) — warunki obecności: [baza-wiedzy.md](baza-wiedzy.md), [7zzx6g], [855g3e].

## Edytor

- **[m22zsg]** Znacznik miejsca w edytorze witryny ([bloki.md](bloki.md), [nv2eze]): „Artykuł — sekcja otwierająca, pasek meta, lead, spis treści, treść i wizytówka autora bieżącego wpisu".
- **[mdp3gt]** Panele wpisu rejestruje skrypt edytora bloku (`registerPlugin`), ładowany w każdym edytorze — panele same sprawdzają typ wpisu i działają tylko dla `post`.
- **[fjwp5e]** Panel „Autor artykułu" ([artykuly.md](artykuly.md), [azuzdc]): lista „Ekspert" — „— bez autora —" (0) i eksperci (typ `ekspert`, bez limitu) alfabetycznie po tytule; pomoc: „Lista: Eksperci w menu panelu. Bez autora — pasek meta bez nazwiska, bez wizytówki".
- **[hfbks8]** Panel „Widoczność na listach" ([artykuly.md](artykuly.md), [a3cg2z]): pole wyboru „Nie pokazuj na listach artykułów" z tekstem pomocy; zakres flagi — [artykuly.md](artykuly.md), [jwnmvv].

## Przykład

```html
<!-- wp:feuer/artykul /-->
```
