# feuer/belka-zapowiedzi

„Belka zapowiedzi" — wąski pas z jedną zapowiedzią dla serwisu (znak graficzny, chip, zdanie, link akcji), wstawiany przez redaktora w treść. Typ: D ([bloki.md](bloki.md), „Typy bloków"). Pola belki: [feuer/belka-zapowiedzi-dane](blok-belka-zapowiedzi-dane.md); sekcja `belka-zapowiedzi`: [sekcje.md](sekcje.md), [yyq58q].

## Gdzie

- **[3nbcgj]** Bez pól, z jednym ustawieniem — „Szerokość tła" (css.md, [k34pyh]; w każdym wstawionym bloku osobno): redaktor wstawia blok w treść stron i wpisów (także strony głównej, między blokami) jako samodzielną sekcję.
- **[64eyy4]** We wpisie belka stoi w karcie treści — układ jak na stronie, w szerokości łamu, także na telefonie (nie na pełną szerokość ekranu).

## Dane

- **[st83u3]** Dwa bloki: ten — wstawiany w treść, renderuje sekcję — i [feuer/belka-zapowiedzi-dane](blok-belka-zapowiedzi-dane.md) z polami belki, w treści sekcji `belka-zapowiedzi`.
- **[usu36x]** Render: treść opublikowanej sekcji `belka-zapowiedzi` (`feuer_sekcja()`, `do_blocks`; jedna sekcja dla wszystkich języków — [sekcje.md](sekcje.md), [8bcbuy]); brak sekcji — na froncie nic (przełącznik „Pokazuj belkę": [feuer/belka-zapowiedzi-dane](blok-belka-zapowiedzi-dane.md), [dv7j3s]).
- **[ppv7dh]** Jedna zapowiedź dla serwisu z jednego miejsca: zmiana w sekcji zmienia belkę wszędzie, gdzie jest wstawiona; bez kilku zapowiedzi, rotacji i planowania publikacji.
- **[vpxre2]** Belka nie przykleja się przy przewijaniu — odjeżdża z treścią (przykleja się wyłącznie header).

## Edytor

- **[yzgbvk]** Podgląd z serwera (`ServerSideRender` w `Disabled`, `render.php` jedynym źródłem HTML), bez pól.
- **[6dz56q]** Pusty render (belka wyłączona albo brak sekcji) — zamiast pustego miejsca informacja dla redaktora z etykietą „Belka zapowiedzi": „Belka jest wyłączona albo nie ma sekcji „belka-zapowiedzi”. Treść i przełącznik „Pokazuj belkę”: Sekcje → Belka zapowiedzi."

## Przykład

```html
<!-- wp:feuer/belka-zapowiedzi /-->
```
