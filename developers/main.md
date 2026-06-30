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

- **Granica świata:** ±2000 na osiach X i Z (promień 2000 od spawnu)
- **Tylko Overworld:** Wymiary Nether i End są wyłączone
- **Seed świata:** Losowo generowany, ukryty przed graczami
- **Ochrona spawnu:** Promień 50 bloków (zarządzane przez Purpur)
- **Anti-Xray:** Tryb silnika 2 włączony (ukrywa rudy jako kamień w nieodkrytych chunkach)

---

## 3. Uwagi operacyjne

### Pre-generacja świata

Świat jest pre-generowany za pomocą Chunky o promieniu 2000. Działa to jako zadanie w tle i nie wymaga przestoju serwera. Gracze mogą kontynuować grę podczas generowania.

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
| **Bezpieczeństwo** | AuthMe, GrimAC, CoreProtect, CombatLogX |
| **Udogodnienia** | BetterSleeping, SimpleScore, TAB |
| **Zarządzanie serwerem** | LuckPerms, Maintenance, AdvancedServerList |
| **Mapa WWW** | BlueMap |
| **Międzywersyjność** | ViaVersion |
| **Świat** | Chunky |

---

## 5. Dostęp graczy

- **Uwierzytelnianie:** Gracze logują się przez hasło AuthMe
- **Whitelista:** Niewymuszona (każdy z poprawnym auth może dołączyć po rejestracji)
- **Ograniczenie krajowe:** Serwer jest ograniczony tylko do Polski (przez CountryBlock) — gracze z innych krajów są blokowani przy próbie połączenia
- **Wykrywanie VPN:** Włączone — gracze używający VPN/proxy są blokowani
- **Maks. graczy:** 20

---

## 6. Przegląd komend

Gracze mają dostęp do wybranego zestawu komend przez LuckPerms, głównie z EssentialsX:

| Grupa komend | Opis |
|---|---|
| `/home`, `/sethome` | Osobiste domy |
| `/tpa`, `/tpahere`, `/tpaccept`, `/tpdeny` | Prośby o teleportację |
| `/spawn` | Powrót do spawnu |
| `/msg`, `/reply` | Prywatne wiadomości |
| `/mail` | Wiadomości offline |
| `/back` | Powrót do ostatniego miejsca śmierci |
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
