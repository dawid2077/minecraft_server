# Tryby gry

> Jak działają tryby gry na serwerze, czego mogą się spodziewać gracze i jak obsługiwane są konkretne aktywności.

---

## Tryb główny: Survival

Domyślny tryb gry dla wszystkich graczy. Świat jest tylko survivalowy, co oznacza:

- **Zdrowie i głód** mają znaczenie — jedz, aby regenerować, unikaj głodu
- **Zarządzanie ekwipunkiem** — przedmioty wypadają po śmierci
- **Kopanie i budowanie** — wszystkie standardowe mechaniki survivalu
- **Potwory** — wrogie moby spawnią się w nocy i w ciemnych miejscach
- **Poziom trudności:** Łatwy (mniej i słabsze wrogie moby)

### PvP

Walka gracz kontra gracz jest **włączona**. Obowiązują wszystkie zasady PvP:

- **Tag bojowy:** 10 sekund po zadaniu lub otrzymaniu obrażeń od innego gracza
- **Combat logging:** Jeśli otagowany gracz wyjdzie, umiera (przedmioty wypadają)
- **Bez bezpiecznego logowania:** Użyj `/spawn` lub ucieknij w bezpieczne miejsce, aby uniknąć PvP

### Śmierć

- Przedmioty wypadają w miejscu śmierci
- Użyj `/back`, aby wrócić do punktu śmierci
- Brak keep-inventory — standardowe konsekwencje survivalu

---

## Administracyjne tryby gry

Dostępne tylko dla operatorów i autoryzowanego personelu przez permisje LuckPerms.

### Kreatywny (`/gamemode creative`)

Pełny kreatywny ekwipunek, latanie, natychmiastowe niszczenie bloków i brak obrażeń. Używane do:

- Budowania i testowania
- Konstrukcji obszaru spawnu
- Przygotowywania wydarzeń
- Edycji i napraw świata

### Widz (`/gamemode spectator`)

Swobodne latanie, tryb bez kolizji. Używane do:

- Inspekcji świata i rozwiązywania problemów
- Obserwowania graczy bez interakcji
- Mapowania i aktualizacji BlueMap

### Przygoda (`/gamemode adventure`)

Nie można niszczyć ani stawiać bloków. Używane do:

- Minigier lub stref zastrzeżonych
- Oprowadzania z przewodnikiem
- Światów eventowych, gdzie budowanie powinno być wyłączone

---

## Zasady świata

| Ustawienie | Wartość |
|---|---|
| **Domyślny tryb gry** | Survival |
| **Wymuszanie trybu gry** | Wył. (przywraca przy zmianie świata) |
| **Poziom trudności** | Łatwy |
| **Hardcore** | Wył. |
| **PvP** | Włączone |
| **Spawning potworów** | Włączony (łatwy poziom) |
| **Spawning zwierząt** | Włączony |

---

## Progresja i funkcje

### Wczesna gra

1. Dołącz do serwera i zarejestruj się przez AuthMe
2. Użyj `/kit tools` po startowe kamienne narzędzia
3. Użyj `/spawn`, aby wrócić do obszaru spawnu
4. Eksploruj od spawnu, aby zająć terytorium
5. Użyj `/sethome` w wybranej lokalizacji bazy

### Środkowa gra

- Zaklęty sprzęt
- Eksploruj do granicy świata (±2000)
- Zbieraj łupy ze zrzutów UltimateAirdrops
- Załóż farmy i produkcję zasobów

### Późna gra

- Buduj wielkoskalowe projekty
- PvP z innymi doświadczonymi graczami
- VeinMiner do efektywnego zbierania zasobów
- Dekoruj używając płyt, schodów i pełnej palety bloków

---

## Wymiary

| Wymiar | Status |
|---|---|
| **Overworld** | ✅ Aktywny (granica świata ±2000) |
| **Nether** | ❌ Wyłączony |
| **End** | ❌ Wyłączony |

Wymiary Nether i End są wyłączone, aby skupić świat na survivalu w pojedynczym, ograniczonym overworldzie. Wszystkie zasoby muszą być pozyskiwane z overworldu.
