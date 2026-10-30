# feuer/terminy-otwarte

„Terminy szkoleń otwartych" (K44) — tabela szkoleń jednej grupy produktów z terminami na najbliższe miesiące: wybór terminu i „Zamów" pod tabelą. Typ: D ([bloki.md](bloki.md), „Typy bloków"). Aktualne terminy: [produkt.md](produkt.md), [d566w4]; grupy produktów: [taksonomie.md](taksonomie.md), „Grupa produktów"; prewypełnienie layeru: formularz-kontaktu.md, „Prewypełnienie".

## Gdzie

- **[bx5mgy]** Samodzielna sekcja w treści stron i produktów (poza paletą treści redakcyjnej) i blok w treści etapu Programu ([README bloku `karta-opisu-produktu-pozycja`](blok-karta-opisu-produktu-pozycja.md), [gzrcmd]) — tam bez odstępów sekcji i kontenera, na szerokość panelu. Wybierak typów szkoleń na stronie składa się z Programu w odmianie „Zakładki": etap = typ (nazwę zakładki wpisuje redaktor), w panelu etapu ten blok.
- **[ctjqq2]** Osobny komponent, nie odmiana Terminów ani Karuzeli szkoleń — wiersze szkoleń z wyborem terminu zamiast kart terminów.

## Pola

| ID | Pole | Atrybut | Rodzaj | Dozwolone | Limit | Wymagane / domyślne |
|---|---|---|---|---|---|---|
| **[7uacps]** | Grupa produktów | `grupa` (ID termu `grupa`) | lista w panelu „Ustawienia": „— wybierz grupę —" (0) i grupy po nazwie | — | — | 0 — bez szkoleń (komunikat braku terminów) |
| **[mnuma9]** | Okres | `okres` | lista w panelu „Ustawienia": 1–6 miesięcy | 1–6; inna wartość daje 3 | — | 3 |

- **[s7htgg]** Teksty bloku („Zamów", tekst ceny w wierszu, komunikat braku terminów) — etykiety interfejsu przez i18n ([bloki.md](bloki.md), [8464y5]); blok nie ma pól tekstowych.

## Dane

- **[4qgdz5]** Szkolenia: opublikowane produkty rodzaju „szkolenie" z wybraną grupą (bez grup podrzędnych), bez flagi „Nie pokazuj w listingu kategorii" ([produkt.md](produkt.md), [999uaf]), w języku strony; kolejność wierszy — kolejność listingu ([strony-zbiorcze.md](strony-zbiorcze.md), [xbcyrc]).
- **[tbyvfz]** Okres N miesięcy: aktualne terminy z datą nie późniejszą niż dzisiejszy dzień miesiąca N miesięcy później (21.10, N = 3 → do 21.01); gdy takiego dnia w tamtym miesiącu nie ma — do jego ostatniego dnia (30.11, N = 3 → do 28.02).
- **[xfmbr9]** Wiersz — szkolenie z co najmniej jednym terminem w okresie (szkolenie bez terminu w okresie nie ma wiersza): z lewej nazwa na karcie ([produkt.md](produkt.md), [hh6g67]) jako link do strony szkolenia, pod nią „Opis w terminach szkoleń otwartych" ([produkt.md](produkt.md), [7fy2wg]) i tekst ceny rozdzielone „·" — „Cena: 300 zł za osobę, zwolnione z VAT", „Cena: 550 zł netto za osobę", przy formularzu z SEP „… + 480,60 zł netto za jedno uprawnienie" (kwota bez groszy, gdy pełne złote; bez ceny — sam opis; `feuer_zapis_cena_tekst()`); pusty opis — „Opis na karcie" (pusty — znacznik pola obowiązkowego, bez zgłoszenia); z prawej kwadraty terminów, od najbliższego.
- **[sxkrs8]** Kwadrat terminu: dzień, skrót miesiąca, skrót dnia tygodnia („18 / lis / śr"; formaty dat przez i18n); termin to jeden dzień — kilka terminów jednego dnia to kilka kwadratów.
- **[ndb3yd]** Klik w kwadrat zaznacza ten termin (pole wyboru, jedno zaznaczenie na tabelę; kolejny klik w inny kwadrat przenosi zaznaczenie) — nie przechodzi na stronę szkolenia; każda tabela na stronie ma własne zaznaczenie i własny przycisk „Zamów". Zaznaczenie nie przetrwa przeładowania strony.
- **[7y4e7u]** Pod tabelą przycisk „Zamów" (A41 ze strzałką), bez tła i bez tekstu, od lewej krawędzi kolumny kwadratów terminów; bez zaznaczenia — nieaktywny; po zaznaczeniu (zaznaczony kwadrat) aktywny i otwiera layer kontaktu z prewypełnieniem (formularz-kontaktu.md, [ga8j4w]), a przy szkoleniu gotowym do zapisu — formularz zapisu z wybranym terminem (formularz-zapisu.md, [ducsaw]).
- **[kcpka6]** Brak wierszy (żadnego terminu w okresie albo grupa niewybrana) — w miejscu tabeli i paska komunikat „W najbliższych N miesiącach nie ma terminów tych szkoleń." (N = 1 — „W najbliższym miesiącu…") z linkiem akcji „Skontaktuj się z nami", który otwiera layer kontaktu bez prewypełnienia (`feuer_brak_produktow()`); blok wyświetla się także bez wierszy.
- **[w2hwn7]** Poniżej 1024 px wiersz w kolumnie — nazwa, opis, pod nimi kwadraty od lewej; przycisk „Zamów" na całą szerokość.

## Edytor

- **[3f7ajd]** Podgląd z serwera (`ServerSideRender`, render jedynym źródłem HTML), nieaktywny — linki i kwadraty terminów w kanwie nie działają; desktop i podgląd poniżej 1024 px jak na froncie.
- **[8sn8va]** Grupa niewybrana — w kanwie zamiast podglądu informacja „Wybierz grupę produktów w ustawieniach bloku. Bez grupy na stronie widać komunikat o braku terminów."

## Wielojęzyczność

- **[zvtus2]** Szkolenia w języku strony, grupa wspólna dla języków ([wielojezycznosc.md](wielojezycznosc.md), [7n3mcs]); daty i forma terminu wspólne, opis terminu — z tłumaczenia szkolenia ([produkt.md](produkt.md), [pyhqcb]); reszta wg [bloki.md](bloki.md), [49nkuy].

## Przykład

```html
<!-- wp:feuer/terminy-otwarte {"grupa":85} /-->

<!-- wp:feuer/terminy-otwarte {"grupa":47,"okres":6} /-->
```
