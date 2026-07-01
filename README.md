# 🧱 Minecraft Survival

> **IP:** `79.76.97.43` · **Wersja:** 1.21.7 · **Oprogramowanie:** [Purpur](https://purpurmc.org/) · **Tryb:** Survival (PvP 🗡️)

---

## ⚡ Szybkie informacje

| | |
|---|---|
| 🖥️ **IP serwera** | `79.76.97.43` |
| 🎮 **Wersja** | 1.21.7 (kompatybilny wstecz przez ViaVersion) |
| 🧩 **Oprogramowanie** | Purpur (fork Paper) |
| 🎯 **Tryb gry** | Survival — PvP włączone (poza spawnem) |
| 🟢 **Poziom trudności** | Łatwy |
| 🌍 **Granica świata** | 2000×2000 bloków |
| 🚫 **Wymiary** | Tylko Overworld (Nether/End wyłączone) |
| 👥 **Maks. graczy** | 20 |
| 📍 **Kraj** | Tylko Polska |
| 🛡️ **Uwierzytelnianie** | AuthMe (premium logowanie bez hasła) |
| 🗺️ **Mapa WWW** | BlueMap (live 3D) |
| 🏠 **Ochrona spawnu** | 50×50 (WorldGuard — brak PvP i niszczenia) |

---

## 📋 Spis treści

- [Informacje o serwerze](#-szybkie-informacje)
- [Jak zacząć?](#-jak-zacząć)
- [Komendy](#-komendy)
- [Drużyny](dlagraczy/teamy.md)
- [Wydarzenia](dlagraczy/events.md)
- [Dokumentacja developerska](#-dokumentacja-developerska)
- [Zmiany (2026-07-01)](#-zmiany-2026-07-01)

---

## 🚀 Jak zacząć?

| Krok | Opis |
|---|---|
| 1️⃣ | Dodaj serwer: **`79.76.97.43`** (port domyślny) |
| 2️⃣ | **Konto premium:** Wejdziesz automatycznie — brak hasła |
| 2️⃣ | **Konto non-premium:** `/register <hasło> <hasło>` |
| 3️⃣ | Weź zestaw startowy: `/kit tools` |
| 4️⃣ | Znajdź miejsce na bazę i ustaw dom: `/sethome` |
| 5️⃣ | Sprawdź mapę online: BlueMap (port 8100) |

---

## 🎮 Komendy

| Komenda | Działanie |
|---|---|
| `/home` / `/sethome` | Teleportacja do twojego domu |
| `/tpa <gracz>` | Wyślij prośbę o teleportację |
| `/spawn` | Powrót do spawnu |
| ~~`/back`~~ | ❌ Wyłączone |
| `/kit tools` | Zestaw startowy narzędzi |
| `/msg <gracz> <tekst>` | Prywatna wiadomość |
| `/rules` | Zasady serwera |
| `/list` | Gracze online |
| `/echest` | Ender chest |
| `/airdrops help` | Dropy na serwerze |
| `/airdrops compass` | Kompas do najbliższego dropu |
| `/vanish` | Niewidzialność (administracja) |

> Pełna lista komend w [dokumentacji](developers/main.md#6-przegląd-komend).

---

## 🔍 Szybkie fakty

| Fakt | Szczegóły |
|---|---|
| 🗺️ **Seed świata** | `2800725041837543666` (reset 2026-07-01) |
| 🔨 **Pre-generacja** | Chunky — 16 129 chunków (100%) |
| 🛡️ **Ochrona spawnu** | 50×50 — WorldGuard (brak PvP, brak niszczenia) |
| 🚫 **VPN/Proxy** | Zablokowane |
| 📦 **Kopie zapasowe** | Codziennie 06:00 GMT, 7 dni wstecz |
| 🧹 **Anty-grief** | CoreProtect + WorldGuard |
| ⚔️ **Combat tag** | 20 sekund (PvP) |
| 🛌 **Pomijanie nocy** | BetterSleeping |
| 🛡️ **Anty-logout** | CombatLogX (20s timer, tylko PvP) |
| 🤖 **Czat z Discordem** | DiscordSRV |

---

## 📝 Zmiany (2026-07-01)

### Nowe pluginy
- **WorldGuard** 7.0.14 + **WorldEdit** 7.3.15 — ochrona spawnu
- **PacketEvents** 2.13.0 — weryfikacja premium w AuthMe

### Zmiany konfiguracji
- **Nowy świat** z seedem `2800725041837543666` (stary: `11195220106425106596`)
- **Spawn chroniony:** 50×50, brak PvP, brak niszczenia (WorldGuard)
- **Anti-logout:** 20s timer (było 10s), tylko PvP (moby nie tagują)
- **Teleport delay:** 10s
- **`/back`:** ❌ Wyłączone
- **Command blocks:** Włączone
- **Render distance:** 32 chunki (max)
- **TAB scoreboard:** Nowy wygląd, sponsor, 100 losowych powitań
- **AuthMe premium:** Premium gracze wchodzą bez hasła
- **Whitelist:** Włączona (4 graczy)
- **Vanish:** Dostępny dla wszystkich na whitelist
- **CoreProtect:** Baza danych zresetowana (świeża)

---

## 📚 Dokumentacja developerska

Szczegółowa dokumentacja architektury serwera, pluginów i konfiguracji:

| Dokument | Opis |
|---|---|
| [`developers/main.md`](developers/main.md) | 🏗️ Architektura serwera — host, stos, kopia zapasowa |
| [`developers/plugins.md`](developers/plugins.md) | 🔌 Pełny indeks pluginów z opisami |
| [`developers/modes.md`](developers/modes.md) | 🎯 Tryby gry i progresja |
| [`developers/rules.md`](developers/rules.md) | ⚖️ Regulamin serwera |
| [`developers/spawn.md`](developers/spawn.md) | 🏠 Spawn i granica świata |
| [`dlagraczy/teamy.md`](dlagraczy/teamy.md) | 🏠 Lista drużyn |
| [`dlagraczy/events.md`](dlagraczy/events.md) | 🎪 Wydarzenia na serwerze |

---

> 🧱 Survival · PvP · Polska 🇵🇱
