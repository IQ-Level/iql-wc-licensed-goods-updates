# Historia wersji — IQL Licensed Goods for WooCommerce

Kanał wersji wtyczki. Instalacje czytają stąd `latest.json` (przycisk „Sprawdź teraz"
w ustawieniach wtyczki). Paczki ZIP dostajesz tam, gdzie kupiłeś wtyczkę.

## 1.0.3 — 2026-11-25

### Nowe
- **Oznaczanie tagiem.** Checkbox „Wymaga pozwolenia” jest teraz także przy tagach
  produktów (Produkty → Tagi). Produkt z takim tagiem jest „na pozwolenie”
  niezależnie od kategorii. Kolumna na liście produktów pokazuje, skąd to wynika
  (z produktu / z kategorii / z tagu).
- **Jasny komunikat dla klienta.** Po dodaniu towaru na pozwolenie do koszyka:
  „… jest dostępny tylko na rezerwację — z odbiorem osobistym i płatnością w sklepie”.
  Gdy w koszyku jest też zwykły towar, koszyk i kasa tłumaczą dwie drogi: wszystko
  jednym zamówieniem z odbiorem i płatnością na miejscu albo zwykłe produkty osobnym
  zamówieniem, a towar na pozwolenie drugim. Teksty edytowalne w ustawieniach.

### Poprawki
- **Kasa klasyczna (Elementor) była zablokowana dla towaru na pozwolenie.**
  Zamiast formularza pokazywała się „There are some issues with the items in your
  cart” — kontrola odbioru osobistego działała, zanim WooCommerce policzył wysyłkę.
- Komunikat w koszyku klasycznym pokazywał się dopiero na następnej stronie.

## 1.0.2 — 2026-11-25

### Poprawki
- **Wygasła lub anulowana rezerwacja zwraca stany magazynowe.** Wcześniej towar
  zdejmowany ze stanu przy rezerwacji nie wracał do sprzedaży po wygaśnięciu ani po
  ręcznym anulowaniu — WooCommerce nie widział, że stan został zdjęty.
- **Oświadczenie w kasie blokowej działa na każdej wersji WooCommerce.** Checkbox
  jest teraz w polu metody „Płatność w sklepie przy odbiorze”, więc pokazuje się tylko
  przy koszyku z towarem na pozwolenie. Bez zaznaczenia zamówienia nie da się złożyć.
- **Odbiór osobisty zaznacza się sam.** Nowsze WooCommerce celowo nie wybiera odbioru
  domyślnie, więc kasa zgłaszała „to zamówienie wymaga opcji wysyłki”. Dla koszyka
  z towarem na pozwolenie odbiór jest jedyną opcją, więc wtyczka wybiera go od razu.
- **Nieudana próba nie blokuje następnej.** Na nowszym WooCommerce komunikat
  o brakującym oświadczeniu zostawał w sesji i odrzucał kolejną, już poprawną próbę.

### Zgodność
- Wymagany WooCommerce obniżony z 8.9 do **8.2** — sklepy na WordPress 6.3 nie mogą
  zainstalować nowszego WooCommerce. Sprawdzone na WP 6.3.5 z WooCommerce 8.2.2 i 8.5.2
  oraz na najnowszym WordPressie i WooCommerce (HPOS).

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
