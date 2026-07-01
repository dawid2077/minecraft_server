# Architektura serwera

> Przegląd techniczny infrastruktury serwera Minecraft, stosu oprogramowania i uwag operacyjnych.

---

## 1. Host i infrastruktura

| Szczegół | Wartość |
|---|---|
| **Typ hosta** | VM (arm64/aarch64) |
| **System operacyjny** | Oracle Linux 9 |
| **Przydzielony RAM** | 8 GB |
| **Rdzenie CPU** | 2 (arm64) |
| **Java** | 21 |
| **Katalog serwera** | `~/minecraft/` |
| **Menedżer procesów** | tmux (sesja: `mc-server`) |
| **Render distance** | 32 chunki (max) |
| **Command blocks** | Włączone |

### Flagii JVM

Serwer działa z zalecanymi flagami Aikara dla G1GC dostrojonymi pod 2-rdzeniowy ARM. Minimalizują one opóźnienia spowodowane garbage collection.

### Zapora sieciowa

- **Port Minecraft:** TCP+UDP 25565 (firewalld + reguły przychodzące w chmurze)
- **Mapa WWW BlueMap:** Port 8100 (firewalld + zapora chmurowa)

---

## 2. Stos oprogramowania

### Oprogramowanie serwera

- **[Purpur](https://purpurmc.org/)** 1.21.7 — fork Paper/Pufferfish z dodatkowymi opcjami konfiguracyjnymi
- **Tryb offline:** `online-mode=false` — uwierzytelnianie delegowane do pluginu AuthMe

### Ustawienia świata

- **Granica świata:** ±1000 na osiach X i Z (2000×2000, 16 129 chunków wygenerowanych)
- **Tylko Overworld:** Wymiary Nether i End są wyłączone
- **Seed świata:** `2800725041837543666` (losowy po resecie 2026-07-01)
- **Stary seed:** `11195220106425106596` (przed resetem)
- **Ochrona spawnu:** Strefa 50×50 bloków (WorldGuard) — brak PvP, brak niszczenia/stawiania
- **OP bypass ochrony:** Wyłączony (`disable-bypass-by-default: true`)
- **Anti-Xray:** Tryb silnika 2 włączony (ukrywa rudy jako kamień w nieodkrytych chunkach)
- **Max render distance:** 32 chunki (view-distance + simulation-distance)

---

## 3. Uwagi operacyjne

### Pre-generacja świata

Świat jest pre-generowany za pomocą Chunky o promieniu 1000 (16 129 chunków). Generowanie zakończone w 100%. Gracze mogą grać bez lagów od generowania nowych chunków.

### Kopie zapasowe

- **Harmonogram:** Codziennie o 06:00 GMT
- **Przechowywanie:** 7 dni (automatyczne czyszczenie starszych kopii)
- **Format:** Spakowany tarball (gzip)
- **Wykluczenia:** Pliki danych graczy (indywidualne ekwipunki/pozycje)
- **Lokalizacja:** `~/minecraft/backups/`

### Tryb konserwacji

Serwer ma przełącznik trybu konserwacji (`/maintenance on` / `/maintenance off`). Po aktywacji MOTD zmienia się, aby wskazać konserwację, a nowe połączenia są blokowane do czasu wyłączenia trybu.

### Uruchamianie / zatrzymywanie serwera

- **Uruchomienie:** Wykonaj `~/minecraft/start.sh` (w tmux)
- **Łagodne zatrzymanie:** Wyślij komendę `stop` do konsoli serwera
- **Wymuszone zatrzymanie:** Wyślij komendę `kill` tylko jeśli łagodne zatrzymanie zawiedzie

---

## 4. Ekosystem pluginów

Zobacz [`plugins.md`](plugins.md) po pełny indeks pluginów.

Kluczowe kategorie pluginów:

| Kategoria | Pluginy |
|---|---|
| **Podstawowa rozgrywka** | EssentialsX, VeinMiner |
| **Bezpieczeństwo** | AuthMe (premium + offline), GrimAC, CoreProtect, CombatLogX |
| **Ochrona spawnu** | WorldGuard + WorldEdit |
| **Udogodnienia** | BetterSleeping, SimpleScore, TAB |
| **Zarządzanie serwerem** | LuckPerms, Maintenance, AdvancedServerList |
| **Mapa WWW** | BlueMap |
| **Międzywersyjność** | ViaVersion |
| **Świat** | Chunky |
| **Premium auth** | PacketEvents (weryfikacja kryptograficzna premium)

---

## 5. Dostęp graczy

- **Uwierzytelnianie:** AuthMe z premium auto-login — premium (Mojang) wchodzą bez hasła, non-premium muszą się zarejestrować
- **Whitelista:** Wymuszona — tylko: EnderMag0220, nuqe_bb, reaperq, Low_Death_Gaming
- **Ograniczenie krajowe:** Serwer jest ograniczony tylko do Polski (przez CountryBlock) — gracze z innych krajów są blokowani przy próbie połączenia
- **Wykrywanie VPN:** Włączone — gracze używający VPN/proxy są blokowani
- **Maks. graczy:** 20

### Znani gracze (OP + whitelist)

- EnderMag0220 (właściciel)
- nuqe_bb
- reaperq
- Low_Death_Gaming
- Yankezz_ (OP, nie na whitelist)
- EnderMag0220 (OP, nie na whitelist)
- Barakuda_opar (OP, nie na whitelist)
- endermag0202 (OP, nie na whitelist)
- Whopper_Junior2 (OP, nie na whitelist)

---

## 6. Przegląd komend

Gracze mają dostęp do wybranego zestawu komend przez LuckPerms, głównie z EssentialsX:

| Grupa komend | Opis |
|---|---|
| `/home`, `/sethome` | Osobiste domy |
| `/tpa`, `/tpahere`, `/tpaccept`, `/tpdeny` | Prośby o teleportację |
| `/spawn` | Powrót do spawnu |
| `/kit` | Zestawy startowe (narzędzia itp.) |
| `/msg`, `/reply` | Prywatne wiadomości |
| `/mail` | Wiadomości offline |
| ~~`/back`~~ | ❌ Wyłączone (Essentials disabled-commands + LP negatywna perm) |
| `/list` | Gracze online |
| `/help` | Pomoc komend |
| `/rules` | Zasady serwera |

### Komendy administracyjne

Komendy admina są chronione przez permisje LuckPerms. Dostępne dla opów/adminów:

- `/maintenance` — Przełącz tryb konserwacji
- `/coreprotect` — Inspekcja bloków i rollback
- `/lp` — Zarządzanie permisjami LuckPerms
- `/gamemode` — Zmiana trybu gry
- `/vanish` — Niewidzialność
- `/echest` — Ender chest (dostępne też dla zwykłych graczy)
- `//wand`, `//pos1`, `//pos2` — WorldEdit selekcja (dla adminów)
- `/rg define`, `/rg flag` — WorldGuard zarządzanie regionami
