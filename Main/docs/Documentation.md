# Main — Dokumentacja techniczna

## Cel modułu
Plik `Main/index.html` tworzy stronę startową projektu Neuroshima i udostępnia użytkownikowi przejście do modułu **Kalkulator**.

## Struktura HTML
- `main` — centralny panel strony.
- `img.logo` — logo ładowane z `../Pliki/Logo.png`.
- `h1` — nagłówek modułu.
- `p` — krótki opis przeznaczenia strony.
- `a.btn` — przycisk/nawigacja do modułu Kalkulator.

## Stylistyka i tokeny
Stylistyka jest zgodna z `DetaleLayout.md`:
- Tło: złożone z dwóch radialnych gradientów, ciemnego linear gradient i koloru bazowego `#211a16`.
- Panele: `--panel` i `--panel2` (`#161210`, `#1d1714`).
- Kolor tekstu: `--text` (`#e2d5c4`) i pomocniczy `--text2` (`#bcab96`).
- Obramowania: `--border` (`#8e4b2a`) i `--border-soft`.
- Akcenty: `--accent` (`#c4602b`), `--accent-dark` (`#8f3f1b`) oraz glow `rgba(196,96,43,0.22)`.
- Zaokrąglenia: `--radius` = 12px.

## Typografia
- Font bazowy: `Trebuchet MS`, `Segoe UI`, `Arial Narrow`, `Arial`, `sans-serif`.
- Nagłówek: `Impact`, `Arial Black`, `Franklin Gothic Heavy`, `sans-serif`.
- `h1` ma skalę `clamp(26px, 4vw, 40px)` i uppercase.

## Interakcje
Przycisk `.btn` ma komplet stanów:
- **normal**: tło `rgba(196,96,43,0.10)` i obramowanie akcentowe,
- **hover/focus-visible**: tło `rgba(196,96,43,0.16)`, `translateY(-1px)`, glow,
- **active**: tło `rgba(196,96,43,0.24)`, powrót pozycji do `translateY(0)`.

## Responsywność
- Panel główny: `width: min(880px, 100%)`.
- Odstępy i rozmiary tekstu realizowane przez `clamp`, aby układ był czytelny od mobile do desktop.
- Logo skalowane responsywnie: `clamp(120px, 16vw, 200px)`.

## Nawigacja
Docelowy link przycisku:
`https://cutelittlegoat.github.io/Neuroshima/Kalkulator/index.html`.
