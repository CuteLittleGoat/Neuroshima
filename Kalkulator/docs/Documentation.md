# Kalkulator — Dokumentacja techniczna

## Cel modułu
Plik `Kalkulator/index.html` jest stroną tymczasową informującą o niedostępności finalnej wersji kalkulatora.

## Struktura HTML
- `section.construction` — panel informacyjny na środku ekranu.
- `h1` — główny napis „Strona w budowie”.
- `p` — opis pomocniczy o planowanym udostępnieniu modułu.

## Styl i zgodność z DetaleLayout.md
Wykorzystane są te same założenia wizualne co w projekcie:
- Tło globalne: radialne gradienty + linear gradient + bazowy kolor `#211a16`.
- Panel: gradient z `--panel2` do `--panel`.
- Obramowanie panelu: `2px solid --border` (`#8e4b2a`).
- Kolor akcentu nagłówka: `--accent` (`#c4602b`).
- Cień panelu: `0 16px 40px rgba(0,0,0,0.42)`.

## Typografia
- Font bazowy: `Trebuchet MS`, `Segoe UI`, `Arial Narrow`, `Arial`, `sans-serif`.
- Font nagłówka: `Impact`, `Arial Black`, `Franklin Gothic Heavy`, `sans-serif`.
- Rozmiar `h1`: `clamp(44px, 9vw, 108px)` dla efektu dużego napisu.
- `h1` ma uppercase, letter spacing `0.07em` i subtelny `text-shadow` w kolorze akcentu.

## Layout
- `body` używa `display: grid` i `place-items: center`, co centruje panel pionowo i poziomo.
- Panel ma szerokość `min(920px, 100%)` i responsywne paddingi przez `clamp`.
- Rozmiar tekstu w `p`: `clamp(14px, 2vw, 20px)`.

## Dostępność
- Sekcja otrzymała `aria-label="Informacja o dostępności strony"`, aby komunikat był łatwiej rozpoznawalny przez technologie asystujące.
