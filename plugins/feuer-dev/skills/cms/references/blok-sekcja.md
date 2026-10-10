# feuer/sekcja

„Sekcja (po slugu)" — wstawia w szablonach i częściach szablonu motywu treść sekcji wskazanej slugiem (np. header i stopka serwisu). Typ: szablonowy ([bloki.md](bloki.md), „Typy bloków"). Typ `sekcja`, zestaw sekcji, ochrona, rozwiązywanie tłumaczeń: [sekcje.md](sekcje.md).

## Gdzie

- **[hf932q]** Wyłącznie szablony i części szablonu motywu: poza wstawiaczem ([bloki.md](bloki.md), [89q53x]), bez zapisu jako blok wielokrotnego użytku ([bloki.md](bloki.md), [ecp7bd]).

## Pola

| ID | Pole | Atrybut | Rodzaj | Dozwolone | Limit | Wymagane / domyślne |
|---|---|---|---|---|---|---|
| **[qpstnw]** | Slug sekcji | `slug` | tekst — ustawiany w szablonie, bez kontrolki w edytorze | slug wpisu typu `sekcja` | — | pusty |

## Dane

- **[7z7wry]** Render: treść opublikowanej sekcji o slugu z atrybutu `slug`, wprost do układu rodzica, bez wrappera (`alignfull` działa jak w treści wpisu); pusty slug, brak sekcji albo sekcja nieopublikowana — blok nic nie wypisuje.

## Edytor

- **[h66vxv]** W edytorze witryny — podgląd treści sekcji (`ServerSideRender`) w trybie nieedytowalnym (`Disabled`).

## Przykład

```html
<!-- wp:feuer/sekcja {"slug":"naglowek-serwisu"} /-->
```
