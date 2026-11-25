# Historia wersji — IQL Licensed Goods for WooCommerce

Kanał wersji wtyczki. Instalacje czytają stąd `latest.json` (przycisk „Sprawdź teraz"
w ustawieniach wtyczki). Paczki ZIP dostajesz tam, gdzie kupiłeś wtyczkę.

## 1.0.1 — 2026-11-25

### Zgodność
- Obniżono wymaganą wersję WordPressa z 6.4 na **6.3** — instalacja blokowała się
  na 6.3.x, choć wtyczka nie używa funkcji dostępnych dopiero od 6.4.

## 1.0.0 — 2026-11-25

Pierwsze wydanie.

Wtyczka pozwala sprzedawać w WooCommerce towary wymagające pozwolenia (broń, amunicja)
w modelu **rezerwacji**: klient rezerwuje online, a płatność i wydanie odbywają się
w sklepie po okazaniu dokumentu. Towar objęty ograniczeniem nie jest sprzedawany online.

### Oznaczanie towarów
- Checkbox „Wymaga pozwolenia" na kategorii produktów, dziedziczony przez podkategorie.
- Na produkcie przełącznik: dziedzicz z kategorii / zawsze wymaga / nigdy nie wymaga.
- Znacznik źródła na liście produktów (z kategorii albo z produktu).

### Karta produktu
- Przycisk „Zarezerwuj do odbioru w sklepie" zamiast „Dodaj do koszyka".
- Komunikat pod przyciskiem i dane strukturalne `InStoreOnly` / odbiór osobisty.

### Koszyk i wysyłka
- Tryb koszyka mieszanego do wyboru: całość do odbioru albo blokada mieszania.
- Przy koszyku z ograniczeniem zostaje tylko odbiór osobisty, a płatność online jest niedostępna.
- Komunikaty działają w koszyku klasycznym i blokowym.

### Rezerwacja i realizacja
- Własna bramka „Płatność w sklepie przy odbiorze" i status „Rezerwacja – czeka na odbiór".
- Oświadczenie w kasie wymagane tylko przy koszyku z ograniczeniem.
- Rezerwacja wygasa po ustawionym czasie (domyślnie 7 dni); przypomnienie i przedłużenie.
- Metabox weryfikacji pozwolenia w zamówieniu; bez weryfikacji nie da się oznaczyć zamówienia jako zrealizowane.
- Osobne maile: rezerwacja przyjęta, nowa rezerwacja do sklepu, przypomnienie, wygaśnięcie.

### Zgodność
- WooCommerce HPOS oraz blokowy koszyk i kasa.
- Prywatność (RODO): domyślnie bez numeru dokumentu; gdy włączony — eksport i usuwanie danych WordPressa.
