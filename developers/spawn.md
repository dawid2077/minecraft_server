# Obszar spawnu i granica świata

> Dokumentacja strefy ochrony spawnu, granicy świata i konfiguracji świata dla trybu survival.

---

## 1. Obszar spawnu

Spawn to centralne centrum, w którym wszyscy gracze pojawiają się przy pierwszym dołączeniu lub po użyciu `/spawn`.

### Ochrona spawnu

- **Promień ochrony:** 50 bloków od spawnu świata (0, 0)
- **Kto może budować:** Tylko operatorzy z permisją `essentials.protect` lub równoważną
- **Co jest chronione:** Niszczenie bloków, stawianie bloków, interakcje z pojemnikami
- **Cel:** Zapobieganie griefingowi spawnu i zachowanie obszaru spawnu do użytku społeczności

### Funkcje spawnu

| Funkcja | Szczegóły |
|---|---|
| **Punkt spawnu** | Spawn świata na (0, ~64, 0) |
| **Budowle społeczności** | Obszar spawnu jest zarezerwowany dla infrastruktury społecznościowej |
| **Informacje** | Hologramy przy spawnie wyświetlają zasady i informacje dla nowych graczy |
| **Spawn przy dołączeniu** | Wyłączony (gracze pojawiają się w miejscu ostatniego wylogowania) |
| **Spawn po śmierci** | Standardowy — gracze odradzają się na spawnie świata |

### Komendy teleportacji

| Komenda | Działanie |
|---|---|
| `/spawn` | Teleportuje cię do spawnu świata |
| `/sethome` | Ustaw osobisty punkt domu (użyj tego w swojej bazie) |
| `/home` | Teleportuj się do swojego osobistego domu |
| `/back` | Wróć do ostatniego miejsca śmierci |

---

## 2. Granica świata

Świat jest ograniczony **twardą granicą** na ±2000 bloków na osiach X i Z.

### Co to oznacza

- Obszar gry to kwadrat 4000×4000 bloków wyśrodkowany na (0, 0)
- Gracze nie mogą chodzić, latać ani teleportować się poza granicę
- Każda budowa, eksploracja czy aktywność musi odbywać się w tym obszarze

### Dlaczego granica?

- Zasoby serwera: Mniejszy świat = mniejsze użycie dysku, szybsze kopie zapasowe, mniej pamięci
- Gęstość graczy: Utrzymuje graczy bliżej siebie dla bardziej społecznego doświadczenia
- Zarządzanie zasobami: Łatwo pre-generować cały świat za pomocą Chunky

---

## 3. Pre-generacja świata

Wszystkie chunki w obrębie granicy są pre-generowane, aby zapewnić płynną rozgrywkę.

| Szczegół | Wartość |
|---|---|
| **Narzędzie** | Chunky |
| **Promień** | 2000 bloków |
| **Wymiary** | Tylko Overworld |
| **Status** | Zadanie w tle (gracze mogą grać podczas generowania) |

Pre-generacja oznacza:
- Brak opóźnień przy ładowaniu chunków podczas eksploracji nowych obszarów
- Teren, jaskinie i struktury są już obliczone
- Anti-Xray działa natychmiastowo we wszystkich obszarach

---

## 4. Podsumowanie konfiguracji świata

| Ustawienie | Wartość |
|---|---|
| **Promień granicy** | 2000 bloków |
| **Centrum granicy** | (0, 0) — spawn świata |
| **Promień spawnu** | 50 bloków chronionych |
| **Odległość widoku** | Domyślna |
| **Spawning potworów** | Włączony (łatwy poziom) |
| **Spawning zwierząt** | Włączony |
| **Anti-Xray** | Tryb silnika 2 (ukrywa rudy) |
| **Nether** | Wyłączony |
| **End** | Wyłączony |
| **Seed świata** | Losowy (ukryty przed graczami) |

---

## 5. Odwiedzanie innych obszarów

### Używanie `/tpa` do odwiedzania innych graczy

System próśb o teleportację pozwala graczom odwiedzać bazy innych:

1. Prośba: `/tpa <nazwagracza>`
2. Cel akceptuje: `/tpaccept <nazwagracza>`
3. Teleportujesz się do ich lokalizacji

### Używanie `/home` do powrotu do swojej bazy

1. Ustaw bazę: `/sethome` (w wybranej lokalizacji)
2. Wróć w dowolnym momencie: `/home`

---

## 6. Mapa

Żywa mapa 3D online jest dostępna przez BlueMap. Renderuje cały świat i aktualizuje się w czasie rzeczywistym.

**Funkcje:**
- Zobacz budowle, teren i lokalizacje graczy na mapie
- Nawiguj po świecie z lotu ptaka
- Przydatne do znajdowania punktów orientacyjnych i planowania tras eksploracji
