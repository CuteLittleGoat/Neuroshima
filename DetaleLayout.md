# Detale layoutu i stylu — pełna dokumentacja modułów (Neuroshima)

Ten plik jest **głównym źródłem prawdy** dla całego projektu Neuroshima: zawiera komplet informacji o fontach, kolorach, tłach, ramkach, cieniach, układach, stanach interakcji oraz wyjątkach formatowania we wszystkich modułach.

Styl projektu ma oddawać:
- **postapokaliptyczny brud i zużycie**,
- **warsztatowo-wojskowy charakter**,
- **czytelność narzędzi użytkowych**,
- klimat **rdzy, pyłu, blachy, benzyny, kurzu i starej techniki**,
- bez efektu „sci-fi neon terminal”, chyba że dotyczy wyjątków specjalnych.

---

## Główne założenia stylistyczne Neuroshimy

### 1) Fundament wizualny
Interfejs ma wyglądać jak połączenie:
- wojskowego segregatora polowego,
- starego terminala warsztatowego,
- zużytego pulpitu z blachy i laminatu,
- papierowej dokumentacji z odręcznymi notatkami,
- tablicy operacyjnej z warsztatu, bunkra lub posterunku.

### 2) Słowa-klucze stylu
- **rdza**
- **popiół**
- **stary metal**
- **przetarta farba**
- **oliwkowe khaki**
- **ostrzegawcza czerwień**
- **techniczny krem / kurz**
- **zużyty panel**
- **przemysłowy minimalizm**
- **brudna czytelność**

### 3) Priorytet UX
Mimo mocnego klimatu:
- dane muszą być czytelne,
- tabele muszą być praktyczne,
- formularze muszą być szybkie,
- warstwa klimatyczna nie może utrudniać pracy MG ani gracza.

---

## Wspólny komponent — przełącznik języka
- W modułach: **GeneratorNazw**, **GeneratorNPC**, **DataBank**, **KalkulatorPostaci**, **Audio**, **Infoczytnik** oraz **DiceRoller** dodano przełącznik języka (select PL/EN).
- Styl selecta:
  - tło: **#181411**,
  - obramowanie: `1px solid var(--border)`,
  - tekst: `var(--text)`,
  - focus: delikatny glow w kolorze akcentu (`box-shadow` w rdzawym pomarańczu),
  - strzałka selecta: ciemna, techniczna, bez połysku.
- Domyślny wybór języka to **Polski**.

---

## Tokeny globalne projektu

### 1) Fonty i typografia

#### 1.1 Fonty lokalne
- Bazowy stos dla całego UI:
  - **"Trebuchet MS", "Segoe UI", "Arial Narrow", Arial, sans-serif**
- Font techniczny / tabelaryczny / kody / liczby:
  - **"Consolas", "Lucida Console", "Courier New", monospace**
- Font nagłówków klimatycznych:
  - **"Impact", "Arial Black", "Franklin Gothic Heavy", sans-serif**

#### 1.2 Zasady użycia fontów
- UI bazowe: font bezszeryfowy, czytelny, lekko „narzędziowy”.
- Tabele, liczby, krótkie parametry, rzuty: monospace.
- Nagłówki sekcji: cięższy font condensed / bold.
- Uppercase używać oszczędnie:
  - nagłówki,
  - taby,
  - etykiety filtrów,
  - ważne akcje.
- Nie używać pełnego uppercase dla długich opisów i treści lore.

#### 1.3 Skala typografii
- Tytuł strony: `clamp(26px, 4vw, 40px)`
- Nagłówek sekcji: `18px–24px`
- Labelki: `12px–13px`
- Tekst bazowy: `14px–16px`
- Tabele: `13px`
- Drobne hinty: `11px–12px`

---

### 2) Kolory, tła, ramki, cienie

#### 2.1 Zmienne CSS (źródło prawdy)
- `--bg`: `#211a16`
- `--bg-grad`:
  - `radial-gradient(circle at 18% 16%, rgba(170, 88, 36, 0.16), transparent 26%)`
  - `radial-gradient(circle at 82% 0%, rgba(107, 117, 71, 0.12), transparent 34%)`
  - `linear-gradient(180deg, rgba(0,0,0,0.18), rgba(0,0,0,0.28))`
  - `#211a16`
- `--panel`: `#161210`
- `--panel2`: `#1d1714`
- `--panel3`: `#241d19`
- `--text`: `#e2d5c4`
- `--text2`: `#bcab96`
- `--muted`: `#8e7c69`
- `--dust`: `#cdbb9b`
- `--steel`: `#6f6d68`
- `--border`: `#8e4b2a`
- `--border-soft`: `rgba(142, 75, 42, 0.45)`
- `--accent`: `#c4602b`
- `--accent-dark`: `#8f3f1b`
- `--accent-2`: `#6b7547`
- `--danger`: `#b13a2f`
- `--warning`: `#d2a13a`
- `--ok`: `#7f8f53`
- `--code`: `#f0e3d2`
- `--glow`: `0 0 22px rgba(196, 96, 43, 0.22)`
- `--glow-soft`: `0 0 14px rgba(196, 96, 43, 0.16)`
- `--shadow`: `0 10px 30px rgba(0,0,0,0.32)`
- `--shadow-deep`: `0 16px 40px rgba(0,0,0,0.42)`
- `--radius`: `10px`
- `--radius-sm`: `6px`
- `--radius-lg`: `14px`
- `--div`: `rgba(196, 96, 43, 0.18)`
- `--hbg`: `rgba(196, 96, 43, 0.08)`
- `--zebra`: `rgba(255,255,255,0.025)`
- `--hover`: `rgba(196, 96, 43, 0.11)`

#### 2.2 Dodatkowe wartości kolorów (literalne)
- Tła przycisków:
  - normal: `rgba(196, 96, 43, 0.10)`
  - hover: `rgba(196, 96, 43, 0.16)`
  - active: `rgba(196, 96, 43, 0.24)`
- Tła paneli pomocniczych:
  - `rgba(255,255,255,0.02)`
  - `rgba(255,255,255,0.035)`
  - `rgba(196,96,43,0.05)`
- Focus ring:
  - `0 0 0 2px rgba(196, 96, 43, 0.26)`
- Tło modalu overlay:
  - `rgba(0,0,0,0.55)`

#### 2.3 Charakter materiałów
- Tła i panele powinny sprawiać wrażenie:
  - przykurzonej blachy,
  - laminatu po przejściach,
  - starego pulpitu technicznego,
  - segregatora lub tablicy ogłoszeń.
- Nie stosować sterylnej czerni `#000` jako głównego tła projektu.
- Nie stosować intensywnej zieleni jako motywu głównego.

---

## Moduł — Main

### 1) Fonty i typografia
#### 1.1 Fonty lokalne
- Bazowy stos całego UI:
  - **"Trebuchet MS", "Segoe UI", "Arial Narrow", Arial, sans-serif**
- Nagłówki:
  - **"Impact", "Arial Black", "Franklin Gothic Heavy", sans-serif**

#### 1.2 Zasady użycia fontów
- Tytuł modułu: uppercase, cięższy font, delikatny `letter-spacing`.
- Przyciski: `font-weight: 700`.
- Teksty pomocnicze `.note`: `font-size: 13px`, kolor `var(--text2)`.

### 2) Kolory, tła, ramki, cienie
#### 2.1 Zmienne CSS (źródło prawdy)
- `--bg`: `var(--bg-grad)`
- `--panel`: `var(--panel)`
- `--border`: `var(--border)`
- `--text`: `var(--text)`
- `--accent`: `var(--accent)`
- `--accent-dark`: `var(--accent-dark)`
- `--glow`: `var(--glow)`
- `--radius`: `10px`

#### 2.2 Dodatkowe wartości kolorów (literalne)
- Tła przycisków:
  - `rgba(196, 96, 43, 0.10)` (normal)
  - `rgba(196, 96, 43, 0.16)` (hover)
  - `rgba(196, 96, 43, 0.24)` (active)
- Cień hover na przycisku:
  - `0 0 16px rgba(196, 96, 43, 0.18)`

### 3) Layout i elementy UI
- `body`: flex, centrowanie w pionie i poziomie, padding `24px`.
- `main`: karta o szerokości `min(920px, 100%)`, tło `--panel`, ramka `2px solid --border`, cień `--shadow + --glow`, zaokrąglenia `--radius`, padding `32px 32px 28px`.
- `.actions`: grid z kolumnami `repeat(auto-fit, minmax(220px, 1fr))` i odstępem `18px 20px`.
- `.btn`: blokowy przycisk z animacją `transform` i `background` przy hover/active.
- Dopuszczalne delikatne tekstury tła:
  - subtelny noise,
  - faint scratches,
  - niska przezroczystość.

### 4) Zwijanie/rozwijanie > 9 linii
- Brak funkcjonalności clamp w module Main.

### 5) Wyjątki i formatowanie specjalne
- Brak wyjątków kolorystycznych lub reguł specjalnych.
- Strona główna ma być najbardziej neutralna i „systemowa” ze wszystkich modułów.

---

## Moduł — GeneratorNazw

### 1) Fonty i typografia
#### 1.1 Fonty lokalne
- Stos bazowy:
  - **"Trebuchet MS", "Segoe UI", "Arial Narrow", Arial, sans-serif**
- Wyniki i bloki techniczne:
  - **"Consolas", "Lucida Console", "Courier New", monospace**

#### 1.2 Zasady użycia fontów
- Etykiety (`label`) mają `font-size: 12px`.
- Treść wyników (`.results`) ma `font-size: 15px`, `line-height: 1.6`.
- Dopuszczalne lekkie zwiększenie `letter-spacing` w etykietach.

### 2) Kolory, tła, ramki, cienie
#### 2.1 Zmienne CSS (źródło prawdy)
- `--bg`: `#211a16`
- `--bg-grad`: zgodne z globalnym `--bg-grad`
- `--panel`: `#161210`
- `--panel-soft`: `rgba(196, 96, 43, 0.06)`
- `--text`: `#e2d5c4`
- `--muted`: `#8e7c69`
- `--border`: `#8e4b2a`
- `--accent`: `#c4602b`
- `--accent-dark`: `#8f3f1b`
- `--glow`: `0 0 22px rgba(196, 96, 43, 0.22)`
- `--divider`: `rgba(196, 96, 43, 0.18)`

#### 2.2 Kolory elementów UI
- `input` i `button`: tło `--panel-soft`, obwódka `1px solid --border`.
- `select`: tło `#181411`.
- `select option`: tło `--panel`, kolor `--text`.
- Focus ring: `box-shadow: 0 0 0 2px rgba(196, 96, 43, 0.22)`.

### 3) Layout i elementy UI
- `body`: tło `--bg-grad`, kolor tekstu `--text`.
- `.wrap`: `width: min(1100px, 100%)`, `padding: 28px 20px 40px`.
- `.panel`: tło `--panel`, ramka `2px solid --border`, `border-radius: 12px`, `box-shadow: var(--shadow)`.
- `.grid`: 4-kolumnowy układ (`1.2fr 1fr 1fr 140px`), przy wąskim ekranie jedna kolumna.
- `.btn`: `max-width: 220px`, tło `rgba(196, 96, 43, 0.10)`, hover/active z mocniejszym tłem i cieniem.
- `.pill`: tło `rgba(0, 0, 0, 0.22)`, obwódka `--border`, `border-radius: 999px`.

### 4) Zwijanie/rozwijanie > 9 linii
- Brak funkcjonalności clamp w module GeneratorNazw.

### 5) Wyjątki i formatowanie specjalne
- Wyniki są prezentowane jako lista wierszy z prefiksem `•`, renderowane w `.results` z `white-space: pre-wrap`.
- GeneratorNazw może mieć lekko „kartotekowy” charakter:
  - numerowane listy,
  - tagi regionów / gangów / pochodzenia,
  - subtelne stemple lub etykiety sekcyjne.

---

## Moduł — DataBank

### 1) Fonty i typografia
#### 1.1 Fonty lokalne
- UI bazowe:
  - **"Trebuchet MS", "Segoe UI", "Arial Narrow", Arial, sans-serif**
- Tabele, liczby, skróty:
  - **"Consolas", "Lucida Console", "Courier New", monospace**
- Nagłówki sekcji:
  - **"Impact", "Arial Black", "Franklin Gothic Heavy", sans-serif**

#### 1.2 Zasady użycia fontów
- Tekst bazowy (`body`): główny font UI.
- Nagłówki i elementy akcentowane (`.title`, `.panelHeader`, `.tab`, `.btn`, `.popoverTitle`, `.modalTitle`): cięższy font nagłówkowy lub pogrubiony wariant UI.
- Teksty tabelaryczne: `font-size: 13px`.
- Tagi cech: `font-size: 11px`.
- Opisy pomocnicze: `font-size: 11–12px`.
- Uppercase tylko w elementach nawigacyjnych i kategoriach.

### 2) Paleta kolorów i efekty
#### 2.1 Zmienne CSS (źródło prawdy)
- `--bg`: `#211a16`
- `--bg-grad`: globalne gradienty + `#211a16`
- `--panel`: `#161210`
- `--panel2`: `#1d1714`
- `--text`: `#e2d5c4`
- `--text2`: `#bcab96`
- `--muted`: `#8e7c69`
- `--code`: `#f0e3d2`
- `--red`: `#b13a2f`
- `--border`: `#8e4b2a`
- `--accent`: `#c4602b`
- `--accent-dark`: `#8f3f1b`
- `--accent-2`: `#6b7547`

#### 2.2 Obwódki, cienie i tła pomocnicze
- `--b`: `rgba(142, 75, 42, .35)` — obwódki aktywne.
- `--b2`: `rgba(142, 75, 42, .20)` — delikatne obwódki.
- `--div`: `rgba(196, 96, 43, .18)` — linie podziału.
- `--hbg`: `rgba(196, 96, 43, .08)` — tła nagłówków.
- `--zebra`: `rgba(255,255,255,.025)` — naprzemienne wiersze.
- `--hover`: `rgba(196, 96, 43, .11)` — hover w tabeli.
- `--glow`: `0 0 22px rgba(196, 96, 43, 0.22)` — mocniejszy glow.
- `--glowH`: `0 0 14px rgba(196, 96, 43, 0.16)` — dodatkowy glow dla tytułów.

#### 2.3 Dodatkowe wartości kolorów (literalne)
- `rgba(240,227,210,.72)` — kolor znaczników sortowania.
- `rgba(240,227,210,.92)` — kolor treści popoverów.
- `rgba(0,0,0,.55)` — tło overlay w modalach.
- `#d2a13a` — kolor wyróżnień ostrzegawczych.
- Zakładki związane z tworzeniem postaci mogą używać jaśniejszego tekstu `--code` z `opacity: .92`.
- Zakładki związane z zagrożeniem, obrażeniami, strefami skażeń lub ciężkimi konsekwencjami mogą używać koloru `--danger`.

### 3) Zasady formatowania tekstu i wyjątki
#### 3.1 Zwykły tekst i łamanie linii
- Komórki używają `.celltext`:
  - `white-space: pre-wrap`
  - `line-height: 1.5`
  - `word-break: normal`
  - `overflow-wrap: normal`

#### 3.2 Wyjątki i style inline (markery w danych)
Aplikacja obsługuje specjalne markery formatowania w danych:
- `{{RED}}...{{/RED}}` → czerwony tekst (`.inline-red`, `color: var(--danger)`).
- `{{B}}...{{/B}}` → pogrubienie (`.inline-bold`).
- `{{I}}...{{/I}}` → kursywa (`.inline-italic`).
- `{{DUST}}...{{/DUST}}` → jaśniejszy techniczny kolor (`.inline-dust`, `color: var(--dust)`).
- `{{WARN}}...{{/WARN}}` → kolor ostrzegawczy (`.inline-warn`, `color: var(--warning)`).

#### 3.3 Wyjątki na czerwony kolor (reguły logiczne)
- Kolumny typu:
  - `Tagi Zagrożeń`
  - `Mutacje`
  - `Skażenia`
  - `Rany`
  - `Konsekwencje`
  - `Broń`
  - `Status`
  mogą mieć czerwone akcenty dla wybranych słów.
- Ręczne markery `{{RED}}` w danych wymuszają czerwony kolor niezależnie od kolumny.

#### 3.4 Wyjątki na przecinki
- Dla kolumn z listami tagów przecinki mogą być renderowane neutralnie:
  - `<span class="keyword-comma">,</span>`
- `.keyword-comma` ma kolor bazowy `var(--text)`.

#### 3.5 Wyjątki na `(str.)` / `(str)` / `(strona)`
- Fragmenty tekstu w nawiasach, które zawierają `str`, `str.`, lub `strona`, są automatycznie oznaczane klasą `.ref`.
- `.ref` ma jaśniejszy kolor (`var(--code)`), co wizualnie odróżnia referencje do stron.
- Reguła działa także wewnątrz stylów inline.

#### 3.6 Formatowanie wierszy specjalnych
- Linie zaczynające się od `*[n]` (np. `*[3]`) są wyróżniane klasą `.caretref` i jaśniejszym kolorem `var(--code)`.

#### 3.7 Specjalne formatowanie kolumny `Zasięg`
- Wartości `Zasięg` są dzielone po `/` i składane na nowo.
- Separatory `/` są wyróżnione klasą `.slash` (`color: var(--dust)`).

### 4) Zwijanie i rozwijanie treści (clamp > 9 linii)

Mechanizm działa dwustopniowo:

#### 4.1 Wstępne wykrycie po liczbie linii danych
- Dla każdej komórki liczona jest liczba linii po `\n`.
- Jeśli jest **więcej niż 10 linii**, komórka jest traktowana jako potencjalnie „clampowalna”.
- W tym trybie:
  - renderowany jest skrót do **pierwszych 9 linii**,
  - na końcu dodawany jest hint „Kliknij aby rozwinąć”.

#### 4.2 Weryfikacja po faktycznej wysokości (linijki wizualne)
Po renderze uruchamia się `ResizeObserver`, który:
- mierzy realną liczbę linii: `scrollHeight / lineHeight`;
- jeśli liczba linii **> 9**, to:
  - zawartość jest obcięta do `max-height = lineHeight * 9`,
  - `overflow` ustawiane jest na `hidden`,
  - dopinany jest `.clampHint` z tekstem:
    - „Kliknij aby rozwinąć” (domyślnie),
    - „Kliknij aby zwinąć” (po rozwinięciu).

#### 4.3 Mechanika kliknięcia
- Kliknięcie w komórkę z klasą `.clampable` przełącza stan w `view.expandedCells`.
- Stan jest zapamiętywany per klucz: `sheet|rowid|col`.
- Po przełączeniu następuje natychmiastowy re-render treści dla tej komórki.

### 5) Wymagania szerokości kolumn (min-width)

Wszystkie wymogi szerokości kolumn są ustawiane w `style.css` przy pomocy selektorów:
`table[data-sheet="..."] th[data-col="..."]` i `td[data-col="..."]`.

Poniżej lista bazowa dla Neuroshimy. Nazwy arkuszy można dopasować do finalnej struktury danych.

#### 5.1 Bronie
- `Nazwa`: **30ch**
- `Typ`: **16ch**
- `Zasięg`: **18ch** (bez zawijania, `white-space: nowrap`)
- `Obrażenia`: **10ch**
- `Amunicja`: **10ch**
- `Cena`: **12ch**
- `Dostępność`: **14ch**
- `Tagi`: **28ch**
- `Opis`: **48ch**

#### 5.2 Pancerze
- `Nazwa`: **28ch**
- `Typ`: **16ch**
- `Pancerz`: **10ch**
- `Cena`: **12ch**
- `Dostępność`: **14ch**
- `Tagi`: **26ch**
- `Opis`: **42ch**

#### 5.3 Umiejętności
- `Nazwa`: **26ch**
- `Powiązanie`: **20ch**
- `Opis`: **54ch**

#### 5.4 Perki / Zdolności / Sztuczki
- `Nazwa`: **28ch**
- `Wymagania`: **28ch**
- `Efekt`: **48ch**
- `Uwagi`: **32ch**

#### 5.5 Mutacje / Skażenia / Rany
- `Nazwa`: **28ch**
- `Poziom`: **10ch**
- `Typ`: **16ch**
- `Efekt`: **52ch**
- `Konsekwencje`: **40ch**

#### 5.6 Ekwipunek
- `Nazwa`: **28ch**
- `Typ`: **16ch**
- `Cena`: **12ch**
- `Waga`: **12ch**
- `Opis`: **46ch**
- `Tagi`: **28ch**

#### 5.7 Frakcje / Lokacje / Organizacje
- `Nazwa`: **28ch**
- `Region`: **18ch**
- `Charakterystyka`: **52ch**
- `Relacje`: **42ch**

### 6) Wymagania układu (layout)
- **Siatka główna**: `main` jest gridem z kolumnami `360px` (panel filtrów) i `1fr` (workspace).
- **Responsywność**: poniżej `980px` layout przechodzi na jedną kolumnę.
- **Sticky nagłówki**: nagłówki tabeli są sticky.
- **Panel filtrów**:
  - tło `--panel2`,
  - ramki `1px solid var(--b)`,
  - sekcje filtrów z lekkim odcięciem `--hbg`.

### 7) Stosowanie tych zasad w innych zakładkach
Jeżeli w przyszłości dodasz nową zakładkę lub kolumny, zasady są następujące:
1. **Najpierw zdefiniuj min-width** w `style.css`.
2. **Dopasuj formatowanie danych** w `app.js`.
3. Upewnij się, że nowe kolumny respektują **reguły clampowania** (>9 linii).
4. Zachowaj priorytet czytelności nad klimatycznością.

---

## Moduł — GeneratorNPC

### 1) Fonty i typografia
#### 1.1 Fonty lokalne
- UI główne:
  - **"Trebuchet MS", "Segoe UI", "Arial Narrow", Arial, sans-serif**
- Pola techniczne, statystyki, bloki eksportu:
  - **"Consolas", "Lucida Console", "Courier New", monospace**
- Karta eksportowana/drukowana:
  - **"Georgia", "Times New Roman", serif**

#### 1.2 Zasady użycia fontów
- Interfejs: półtechniczny, czytelny, bez pełnego „terminalowego” charakteru.
- Nagłówki, przyciski, taby, labelki: uppercase z umiarkowanym `letter-spacing`.
- Karta eksportowana: układ bardziej papierowy i dokumentowy niż futurystyczny.

### 2) Kolory, tła, ramki, cienie
#### 2.1 Zmienne CSS (UI główne)
- `--bg`: `#211a16`
- `--bg-grad`: zgodne z globalnym `--bg-grad`
- `--panel`, `--panel2`: `#161210`, `#1d1714`
- `--text`: `#e2d5c4`
- `--text2`: `#bcab96`
- `--muted`: `#8e7c69`
- `--code`: `#f0e3d2`
- `--red`: `#b13a2f`
- `--border`: `#8e4b2a`
- `--accent`: `#c4602b`
- `--accent-dark`: `#8f3f1b`
- `--b`: `rgba(142, 75, 42, 0.35)`
- `--b2`: `rgba(142, 75, 42, 0.20)`
- `--div`: `rgba(196, 96, 43, 0.18)`
- `--hbg`: `rgba(196, 96, 43, 0.08)`
- `--zebra`: `rgba(255,255,255,0.025)`
- `--hover`: `rgba(196, 96, 43, 0.11)`
- `--glow`: `0 0 22px rgba(196, 96, 43, 0.22)`
- `--glowH`: `0 0 14px rgba(196, 96, 43, 0.16)`

#### 2.2 Dodatkowe tła sekcji
- `rgba(196, 96, 43, 0.03)`
- `rgba(196, 96, 43, 0.04)`
- `rgba(196, 96, 43, 0.05)`
- `rgba(196, 96, 43, 0.06)`
- `rgba(196, 96, 43, 0.08)`
- `rgba(196, 96, 43, 0.14)`

#### 2.3 Kolory karty eksportowanej (print HTML)
- Tło `body`: `#f4efe7`
- Tekst bazowy: `#1a1816`
- Nagłówki i belki: `#3a2a20` (tło), `#f8f4ee` (tekst)
- Linie/ramki: `#342821`
- Pasy wierszy:
  - `#e9e0d4` (nagłówki),
  - `#f1ebe2` (naprzemienne wpisy),
  - `#d8cbbd` (separatory wpisów)
- Sekcje checkboxów / zdrowia / statusów:
  - obramowanie `1px solid #342821`,
  - pola aktywne mogą używać `#d7cab8`,
  - pola neutralne `#f8f4ee`.

### 3) Wyjątki formatowania i specjalne reguły tekstu
- **Markery inline**:
  - `{{RED}}...{{/RED}}` → `.inline-red`
  - `{{B}}...{{/B}}` → `.inline-bold`
  - `{{I}}...{{/I}}` → `.inline-italic`
  - `{{WARN}}...{{/WARN}}` → kolor ostrzegawczy
- **Słowa kluczowe** (`.keyword-red`) — kolumny związane z mutacjami, ranami, zagrożeniami lub ciężkimi efektami mogą być czerwone.
- **Wyjątki na przecinki**: w kolumnach list tagów przecinki dostają klasę `.keyword-comma` z kolorem bazowym.
- **`*[n]` na początku linii** → `.caretref`.
- **`Zasięg`**: separator `/` wyróżniony `.slash`.
- **Referencje do stron** (`str`, `str.`, `strona`) → `.ref`.

### 4) Zwijanie/rozwijanie > 9 linii
- Stała `CLAMP_LINES = 9`.
- Komórki z > 10 liniami danych stają się kandydatami do clampa.
- `ResizeObserver` mierzy `scrollHeight / lineHeight`.
- Jeśli > 9:
  - `.is-clampable`,
  - `max-height = lineHeight * 9`,
  - `overflow: hidden`,
  - hint `.clamp-hint`: „Kliknij aby rozwinąć” / „Kliknij aby zwinąć”.
- Stan ekspansji zapisany w `state.expandedCells`.

### 5) Layout i elementy UI
- Górny pasek (`.topbar`) sticky.
- Panele boczne i workspace w układzie `grid` (`360px` + `1fr`).
- Panele z `box-shadow: var(--shadow)` i `border: 1px solid var(--div)`.
- Tabele: zebra i hover oparte o `--zebra` i `--hover`.
- GeneratorNPC powinien mieć lekko „kartę personalną / dossier” vibe.

---

## Moduł — Kalkulator

Moduł składa się z trzech stron:
- `index.html` (landing),
- `KalkulatorXP.html` (kalkulator doświadczenia / rozwoju),
- `TworzeniePostaci.html` (generator postaci).

Wspólny styl bazowy pochodzi z głównego pliku stylów kalkulatora, a dodatkowe style inline są dopuszczalne wyłącznie dla wyjątków komponentowych.

### 1) Fonty i typografia
#### 1.1 Fonty lokalne
- **"Trebuchet MS", "Segoe UI", "Arial Narrow", Arial, sans-serif**
- Dla liczb, kosztów i parametrów:
  - **"Consolas", "Lucida Console", "Courier New", monospace**

#### 1.2 Zasady użycia fontów
- Uppercase i `letter-spacing` w nagłówkach, panelach, tabach.
- `title` i `panelHeader` mogą mieć subtelny `text-shadow` oparty o `var(--glowH)`.
- Pola liczbowe i koszty: monospace.

### 2) Kolory, tła, ramki, cienie
#### 2.1 Zmienne CSS
- `--bg`: `#211a16`
- `--bg-grad`: zgodne z globalnym `--bg-grad`
- `--panel`, `--panel2`: `#161210`, `#1d1714`
- `--text`: `#e2d5c4`
- `--text2`: `#bcab96`
- `--muted`: `#8e7c69`
- `--code`: `#f0e3d2`
- `--red`: `#b13a2f`
- `--border`: `#8e4b2a`
- `--accent`: `#c4602b`
- `--accent-dark`: `#8f3f1b`
- `--b`: `rgba(142,75,42,.35)`
- `--b2`: `rgba(142,75,42,.2)`
- `--div`: `rgba(196,96,43,.18)`
- `--hbg`: `rgba(196,96,43,.08)`
- `--zebra`: `rgba(255,255,255,.025)`
- `--hover`: `rgba(196,96,43,.11)`
- `--glow`: `0 0 22px rgba(196, 96, 43, 0.22)`
- `--glowH`: `0 0 14px rgba(196, 96, 43, 0.16)`

#### 2.2 Dodatkowe wartości kolorów (literalne)
- Tła kart, nagłówków i tabów:
  - `rgba(196,96,43,.03)`
  - `rgba(196,96,43,.04)`
  - `rgba(196,96,43,.05)`
  - `rgba(196,96,43,.06)`
  - `rgba(196,96,43,.08)`
  - `rgba(196,96,43,.10)`
  - `rgba(196,96,43,.12)`
- Cienie i obrysy focus:
  - `rgba(196,96,43,.18)`
- Kolor wskaźnika `.caret`:
  - `rgba(196,96,43,.65)`
- Hover w przyciskach landing page:
  - `rgba(196, 96, 43, 0.16)`
  - `rgba(196, 96, 43, 0.24)`
- Cień hover:
  - `0 0 16px rgba(196, 96, 43, 0.18)`

### 3) Layout i elementy UI
- `index.html`: layout jak Main.
- `KalkulatorXP.html`:
  - `.main`: grid `360px` + `1fr`
  - `.panel`, `.workspace`: ramki `1px solid var(--b)` + subtelny inset shadow
  - `.dataTable`: `font-size: 13px`, zebra i hover z `--zebra` / `--hover`
- `TworzeniePostaci.html`:
  - `.wrapper`: max szerokość `1100px`
  - panel z `border-radius: 10px`
  - `.table`: nagłówki odcięte kolorem `--hbg`, wiersze zebra
  - `textarea`: `resize: none`

### 4) Zwijanie/rozwijanie > 9 linii
- Brak clampowania treści w module Kalkulator.

### 5) Wyjątki i formatowanie specjalne
- `.error-message` używa koloru `var(--danger)`.
- Sekcje wyboru pochodzenia, profesji, archetypu lub pakietu startowego mogą używać delikatnego akcentu `--accent-2`.

---

## Moduł — DiceRoller

### 1) Fonty i typografia
#### 1.1 Fonty lokalne
- Stos bazowy:
  - **"Trebuchet MS", "Segoe UI", "Arial Narrow", Arial, sans-serif**
- Wyniki i formuły:
  - **"Consolas", "Lucida Console", "Courier New", monospace**

#### 1.2 Zasady użycia fontów
- Nagłówek `h1`: `font-size: 30px`, uppercase, `letter-spacing: 0.05em`.
- Formuła rzutu, breakdown i podsumowania używają monospace.
- Podtytuł i opisy pomocnicze używają `--muted`.

### 2) Kolory, tła, ramki, cienie
#### 2.1 Zmienne CSS
- `--bg`: globalne gradienty + `#211a16`
- `--panel`: `#161210`
- `--border`: `#8e4b2a`
- `--text`: `#e2d5c4`
- `--accent`: `#c4602b`
- `--accent-dark`: `#8f3f1b`
- `--muted`: `rgba(226, 213, 196, 0.72)`
- `--glow`: `0 0 22px rgba(196, 96, 43, 0.22)`
- `--radius`: `10px`

#### 2.2 Kolory kości
- `--die-light`: `#efe5d6`
- `--die-light-pip`: `#201814`
- `--die-dark`: `#6d2a1d`
- `--die-dark-pip`: `#f8f0e6`
- `--die-warning`: `#d2a13a`
- `--die-danger`: `#b13a2f`

#### 2.3 Dodatkowe wartości kolorów (literalne)
- Cienie kości:
  - `rgba(0, 0, 0, 0.2)`
  - `rgba(0, 0, 0, 0.35)`
- Obramowania kości:
  - `#3a2d24`
  - `#4e1d14`
- Fokus inputów:
  - `box-shadow: 0 0 0 2px rgba(196, 96, 43, 0.25)`
- Podsumowanie `.summary`:
  - tło `rgba(196, 96, 43, 0.10)`
  - ramka `rgba(196, 96, 43, 0.35)`
- Hover/active przycisku:
  - `rgba(196, 96, 43, 0.16)` / `rgba(196, 96, 43, 0.24)`

### 3) Layout i elementy UI
- Aplikacja centrowana jak w Main (`body` flex + padding `24px`).
- `.panel`: grid z `repeat(auto-fit, minmax(220px, 1fr))`.
- Kości:
  - kwadraty `68px`
  - mobile `58px`
  - animacja `@keyframes roll`
- Wyniki powinny mieć klimat „mechaniki stołowej”, a nie kasynowy.

### 4) Zwijanie/rozwijanie > 9 linii
- Brak clampowania treści w module DiceRoller.

### 5) Wyjątki i formatowanie specjalne
- Brak wyjątków tekstowych; specjalne style dotyczą kości, wyników i breakdownów.
- Nie stosować neonowych efektów arcade.

---

## Moduł — Audio

### 1) Fonty i typografia
#### 1.1 Fonty lokalne
- **"Trebuchet MS", "Segoe UI", "Arial Narrow", Arial, sans-serif**
- Techniczne drobiazgi, timestampy i kody:
  - **"Consolas", "Lucida Console", "Courier New", monospace**

#### 1.2 Zasady użycia fontów
- Tytuł `.title`: uppercase, `letter-spacing: 0.08em`, `font-size: clamp(22px, 3vw, 28px)`.
- Podtytuł `.subtitle`: `font-size: 15px`, `opacity: 0.9`.
- Nazwy sampli i grup powinny być czytelne i krótkie.

### 2) Kolory, tła, ramki, cienie
#### 2.1 Zmienne CSS
- `--bg`: globalne gradienty + `#211a16`
- `--panel`: `#161210`
- `--border`: `#8e4b2a`
- `--text`: `#e2d5c4`
- `--accent`: `#c4602b`
- `--accent-dark`: `#8f3f1b`
- `--danger`: `#b13a2f`
- `--warning`: `#d2a13a`
- `--glow`: `0 0 22px rgba(196, 96, 43, 0.22)`
- `--radius`: `10px`

### 3) Layout i elementy UI
- Układ karty identyczny jak Main (`width: min(860px, 100%)`, centrowanie, `box-shadow: var(--shadow)`).
- Karty sampli:
  - nazwa i tag mają klasę `.sample-trigger`
  - aktywne odtwarzanie dodaje `.is-playing`
  - `.is-playing` może barwić nazwę na `--danger` albo `--warning`, zależnie od typu audio
- Suwak głośności:
  - `.volume-slider`
  - `width: 100%`
  - `accent-color: var(--accent)`

### 4) Zwijanie/rozwijanie > 9 linii
- Brak clampowania treści w module Audio.

### 5) Wyjątki i formatowanie specjalne
- `.group-count`: licznik w nawiasie może być kolorowany `var(--warning)`.
- `.sample-alias`: alias w nawiasie ma jaśniejszy kolor `var(--dust)`.
- Moduł Audio może mieć delikatnie bardziej „panel operatorski” charakter niż inne moduły.

---

## Moduł — Infoczytnik

Moduł składa się z dwóch stron oraz strony startowej:
- **Infoczytnik.html** — ekran graczy,
- **GM.html** — panel prowadzącego,
- **index.html** — menu wyboru wersji.

### 1) Fonty i typografia
#### 1.1 Fonty lokalne
- Domyślny stos:
  - **"Trebuchet MS", "Segoe UI", Arial, sans-serif**
- Teksty techniczne i podgląd:
  - **"Consolas", "Courier New", monospace**
- Nagłówki alarmowe / komunikaty specjalne:
  - **"Impact", "Arial Black", sans-serif**

#### 1.2 Zasady użycia fontów
- `Infoczytnik.html`: rozmiary dynamiczne przez `clamp(...)`
  - `--msg-font-size: clamp(18px, 3.4vw, 32px)`
  - `--prefix-font-size: clamp(12px, 2vw, 16px)`
  - `--suffix-font-size: clamp(12px, 2vw, 16px)`
- `GM.html`: UI panelowy, nagłówki `font-size: 20px`, labelki `font-size: 13px`, podglądy `font-size: 12–16px`.
- `index.html`: stylistyka jak Main.

### 2) Kolory, tła, ramki, cienie
#### 2.1 Infoczytnik.html (ekran graczy)
- Akcent bazowy: `--accent = #d08a3b`
- Tło globalne i panelu: `#0f0c0a`
- Tekst główny: `#f0e3d2`
- Tekst prefix/suffix:
  - `rgba(240,227,210,.84)`
  - `rgba(240,227,210,.72)`
- Overlay zabrudzeń / skanów / pyłu:
  - `rgba(255,255,255,.03)`
  - `rgba(0,0,0,.14)`
  - `rgba(0,0,0,.28)`
- Cienie tekstu:
  - `0 2px 6px rgba(0,0,0,.55)`
  - `0 0 16px rgba(196,96,43,.16)`

#### 2.2 GM.html (panel prowadzącego)
- Zmienne:
  - `--text: #e8dccd`
  - `--muted: #baa792`
  - `--accent: #c4602b`
  - `--border: #3b2e27`
  - `--panel: rgba(22,18,16,.94)`
- Tło strony:
  - `linear-gradient(180deg, #14100d, #1d1714)`
- Przycisk podstawowy:
  - `linear-gradient(180deg, #5a301a, #341b0f)`
  - ramka `rgba(196,96,43,.35)`
- Przycisk ostrzegawczy:
  - `linear-gradient(180deg, #4a1c18, #2b100d)`
  - ramka `rgba(177,58,47,.30)`
  - tekst `#f0c0b8`
- Pola input:
  - tło `#181411`

#### 2.3 index.html (menu wyboru wersji)
- Paleta zgodna z modułem Main:
  - `--bg`: globalne gradienty + `#211a16`
  - `--panel`: `#161210`
  - `--border`: `#8e4b2a`
  - `--text`: `#e2d5c4`
  - `--accent`: `#c4602b`
  - `--accent-dark`: `#8f3f1b`
  - `--glow`: `0 0 22px rgba(196, 96, 43, 0.22)`
  - `--radius`: `12px`
- Notatki i opisy:
  - teksty pomocnicze: `rgba(226, 213, 196, 0.75)`
  - kod w notatkach: `#f0e3d2`

### 3) Layout i elementy UI
- Ekran graczy:
  - `screen` ma pozycję i padding sterowane zmiennymi
  - dopuszczalne są warstwy:
    - kurz / noise,
    - lekkie zabrudzenie,
    - drobna winieta
- Panel GM:
  - `.wrap` max `980px`
  - karta `.card` z cieniem `0 10px 30px rgba(0,0,0,.35)`
  - układ kolumn przez `.row` i `.col`
- `index.html`:
  - `body` centrowany flexem, padding `24px`
  - `main` o szerokości `min(880px, 100%)`
  - sekcje `.section` z delikatnym tłem `rgba(196, 96, 43, 0.05)` i obwódką `rgba(196, 96, 43, 0.35)`
  - przyciski `.btn` dziedziczą styl główny

### 4) Zwijanie/rozwijanie > 9 linii
- Brak clampowania treści w Infoczytniku.

### 5) Wyjątki i formatowanie specjalne
- Kolor treści, prefixu i suffixu może być zmieniany przez GM.
- Dopuszczalne są warianty stylu dla:
  - komunikatu alarmowego,
  - komunikatu technicznego,
  - notki fabularnej,
  - wiadomości radiowej,
  - odczytu terminala.
- Domyślny wariant nie może być zbyt futurystyczny; powinien przypominać zużyty ekran urządzenia terenowego.

---

## Reguły materiałowe i dekoracyjne dla całego projektu

### 1) Tekstury i tła
Dozwolone:
- delikatny noise,
- rysy,
- drobne zadrapania,
- kurz,
- subtelne przebarwienia,
- ślady zużycia na krawędziach.

Niedozwolone:
- mocny grunge utrudniający czytelność,
- przesadnie czyste flat UI bez klimatu,
- cyberpunkowy neon jako dominujący motyw,
- sterylny corporate UI.

### 2) Ramki i separatory
- Ramki powinny wyglądać jak:
  - blacha,
  - nitowana płyta,
  - zużyta osłona panelu,
  - techniczna wkładka.
- Preferowane grubości:
  - `1px` dla standardowych pól,
  - `2px` dla paneli głównych,
  - `1px dashed` lub `1px solid rgba(...)` dla lekkich separatorów technicznych.

### 3) Cienie
- Cienie mają budować głębię, nie efekt „glow sci-fi”.
- Glow stosować oszczędnie:
  - głównie na hover,
  - focus,
  - aktywnych nagłówkach,
  - ważnych przyciskach.

### 4) Ikony i piktogramy
- Styl:
  - techniczny,
  - wojskowy,
  - prosty,
  - stencil / signage / warsztat.
- Unikać:
  - zbyt gładkich rounded icon packs,
  - pastelowych ikon,
  - futurystycznych hologramów.

---

## Zasady stanów interaktywnych

### 1) Hover
- Zmiana tła na mocniejszy wariant akcentu.
- Lekki wzrost kontrastu.
- Minimalne przesunięcie `transform: translateY(-1px)` dopuszczalne dla przycisków.

### 2) Active
- Tło ciemniejsze / bardziej nasycone.
- Delikatny `transform: translateY(0)` lub subtelne „wciśnięcie”.

### 3) Focus
- Wyraźny, ale estetyczny focus ring:
  - `0 0 0 2px rgba(196, 96, 43, 0.26)`
- Focus ma być zawsze widoczny dla klawiatury.

### 4) Disabled
- Obniżony kontrast:
  - tekst `opacity: .45–.60`
  - tło bardziej matowe
  - brak glow
- Disabled ma wyglądać jak „niedostępny zasób”, nie jak błąd.

---

## Zasady semantycznych kolorów

### 1) Kolor podstawowy
- `--accent: #c4602b`
- Użycie:
  - aktywne przyciski,
  - zaznaczenia,
  - focus,
  - aktywne taby,
  - kluczowe akcje.

### 2) Kolor pomocniczy
- `--accent-2: #6b7547`
- Użycie:
  - status neutralno-pozytywny,
  - informacje kontekstowe,
  - poboczne oznaczenia frakcji / regionu / typu.

### 3) Kolor ostrzegawczy
- `--warning: #d2a13a`
- Użycie:
  - ostrzeżenia,
  - ryzyko,
  - ograniczone zasoby,
  - alerty umiarkowane.

### 4) Kolor niebezpieczeństwa
- `--danger: #b13a2f`
- Użycie:
  - błędy,
  - ciężkie obrażenia,
  - skażenie,
  - alarm,
  - efekt krytyczny.

### 5) Jasny techniczny kolor
- `--dust` / `--code`
- Użycie:
  - referencje,
  - skróty,
  - elementy pomocnicze,
  - wartości wymagające wysokiej czytelności.

---

## Zasady projektowe dla przyszłych modułów

Jeżeli w przyszłości dodasz nowy moduł, należy:
1. Bazować na globalnych tokenach tego pliku.
2. Zachować tła `--bg-grad` i materiały panelowe `--panel`, `--panel2`.
3. Zachować główny akcent `--accent` i nie zastępować go innym kolorem bez wpisania wyjątku w tym pliku.
4. Ograniczać liczbę nowych kolorów lokalnych.
5. Najpierw pilnować czytelności danych, potem klimatu.
6. Każdy nowy wyjątek formatowania dopisać do tego dokumentu.

---

## Uwaga końcowa
Każda modyfikacja stylu w dowolnym module **musi** być odzwierciedlona w tym pliku, aby zachować spójne, kompletne źródło prawdy dla stylów całej aplikacji.

Ten dokument definiuje estetykę Neuroshima jako:
- **postapo użytkowe**,
- **brudne, ale czytelne**,
- **wojskowo-warsztatowe**,
- **rdzawe, pyliste i techniczne**,
- **bardziej „schron / warsztat / posterunek” niż „terminal SF”**.
