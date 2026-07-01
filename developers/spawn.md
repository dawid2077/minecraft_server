# Obszar spawnu i granica świata

> Dokumentacja strefy ochrony spawnu, granicy świata i konfiguracji świata dla trybu survival.

---

## 1. Obszar spawnu

Spawn to centralne centrum, w którym wszyscy gracze pojawiają się przy pierwszym dołączeniu lub po użyciu `/spawn`.

### Ochrona spawnu (WorldGuard)

Strefa 50×50 bloków wokół (0, 0) chroniona przez WorldGuard:

- **Wymiary:** od -25 do 25 w X/Z, od 0 do 320 w Y
- **PvP:** ❌ Zablokowane — nie można walczyć na spawnie
- **Niszczenie bloków:** ❌ Zablokowane
- **Stawianie bloków:** ❌ Zablokowane
- **OP bypass:** ❌ Wyłączony — ochrona działa na wszystkich

### Ustawienia serwera

| Funkcja | Szczegóły |
|---|---|
| **Punkt spawnu** | Spawn świata na (0, ~64, 0) |
| **Render distance** | 32 chunki (max) |
| **Command blocks** | Włączone |
| **Ochrona vanilla** | `spawn-protection=50` (w tle, WorldGuard nadrzędny) |
| **Spawn przy dołączeniu** | Wyłączony (gracze pojawiają się w miejscu ostatniego wylogowania) |
| **Spawn po śmierci** | Standardowy — gracze odradzają się na spawnie świata |

### Komendy teleportacji

| Komenda | Działanie |
|---|---|
| `/spawn` | Teleportuje cię do spawnu świata |
| `/sethome` | Ustaw osobisty punkt domu |
| `/home` | Teleportuj się do swojego osobistego domu |
| `/tpa <gracz>` | Wyślij prośbę o teleportację do gracza |
| `/back` | ❌ Wyłączone |
| `/echest` | Otwiera ender chest (dla wszystkich) |

---

## 2. Granica świata

Świat jest ograniczony **twardą granicą** 2000×2000 bloków (radius 1000 od 0,0 na X i Z).

### Co to oznacza

- Obszar gry to kwadrat 2000×2000 bloków wyśrodkowany na (0, 0)
- Gracze nie mogą chodzić, latać ani teleportować się poza granicę
- Wszystkie 16 129 chunków w obrębie granicy jest pre-generowanych

### Dlaczego granica?

- Zasoby serwera: Mniejszy świat = mniejsze użycie dysku, szybsze kopie zapasowe, mniej pamięci
- Gęstość graczy: Utrzymuje graczy bliżej siebie dla bardziej społecznego doświadczenia

---

## 3. Pre-generacja świata

Wszystkie chunki w obrębie granicy są pre-generowane (100% ukończenia).

| Szczegół | Wartość |
|---|---|
| **Narzędzie** | Chunky |
| **Promień** | 1000 bloków (16 129 chunków) |
| **Wymiary** | Tylko Overworld (Nether i End wyłączone) |
| **Status** | ✅ Zakończone |

---

## 4. Podsumowanie konfiguracji świata

| Ustawienie | Wartość |
|---|---|
| **Granica świata** | 2000×2000 bloków (radius 1000) |
| **Seed** | `2800725041837543666` (nowy od 2026-07-01) |
| **Stary seed** | `11195220106425106596` |
| **Pre-generacja** | 16 129 chunków (100%) |
| **Ochrona spawnu** | WorldGuard + vanilla spawn-protection |
| **Render distance** | 32 chunki |
| **Command blocks** | Włączone |
| **Anti-Xray** | Tryb silnika 2 |
| **Nether** | ❌ Wyłączony |
| **End** | ❌ Wyłączony |
| **PvP na spawnie** | ❌ Zablokowane |

---

## 5. Mapa

Żywa mapa 3D online przez BlueMap (port 8100). Renderuje cały świat i aktualizuje się w czasie rzeczywistym.
