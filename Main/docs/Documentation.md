# Main — Dokumentacja techniczna

## Cel modułu
Plik `Main/index.html` tworzy stronę startową projektu Neuroshima i udostępnia użytkownikowi przejście do modułu **Kalkulator**.

## Struktura HTML
- `main` — centralny panel strony.
- `img.logo` — logo ładowane z `../Pliki/Logo.png`.
- `h1` — nagłówek modułu.
- `p` — krótki opis przeznaczenia strony.
- `a.btn` — przycisk/nawigacja do modułu Kalkulator.

## Struktura warstw wizualnych (background stack)
Tło jest budowane warstwowo i składa się z dwóch poziomów:
1. **Bazowe tło `body`**
   - `radial-gradient(circle at 18% 16%, rgba(170, 88, 36, 0.16), transparent 26%)`
   - `radial-gradient(circle at 82% 0%, rgba(107, 117, 71, 0.12), transparent 34%)`
   - `linear-gradient(180deg, rgba(0,0,0,0.18), rgba(0,0,0,0.28))`
   - kolor bazowy `#211a16` (`--bg`)
2. **Warstwa plam rdzy (`body::after`)**
   - osiem radialnych plam (elipsy) rozmieszczonych przy krawędziach viewportu
   - dominujące kolory: `rgba(149, 70, 28, 0.38)`, `rgba(112, 52, 23, 0.35)`, `rgba(160, 77, 34, 0.33)`
   - ciemniejsze centra plam: `rgba(65, 28, 15, 0.43)` i pokrewne
   - wykończenie: `filter: blur(0.4px) saturate(108%)`, `opacity: 0.65`

Pseudo-element rdzy jest ustawiony jako `position: fixed`, `inset: 0`, `pointer-events: none`, `z-index: -1`, a `body` ma `position: relative` i `isolation: isolate`, dzięki czemu dekoracja działa na całym tle i nie blokuje interakcji.

## Stylistyka i tokeny
Stylistyka jest zgodna z `DetaleLayout.md`:
- Tło bazowe: ciepłe, ciemne i przykurzone (`--bg`, gradienty radialne i liniowy).
- Klimat materiału: nieregularne plamy korozji imitujące rdzawą blachę.
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
- Logo skalowane do maksymalnej szerokości panelu (`width: 100%`, `max-width: 100%`) z zachowaniem proporcji (`height: auto`, `object-fit: contain`), z ograniczeniem wysokości do `min(50vh, 460px)`, aby mieściło się w widoku bez deformacji.
- Dekoracja tła (`::after`) działa niezależnie od rozmiaru ekranu, bo jest przypięta do całego viewportu (`position: fixed`).

## Nawigacja
Docelowy link przycisku:
`https://cutelittlegoat.github.io/Neuroshima/Kalkulator/index.html`.
