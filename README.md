# 🧱 Minecraft Survival

> **IP:** `79.76.97.43` · **Wersja:** 1.21.7 · **Oprogramowanie:** [Purpur](https://purpurmc.org/) · **Tryb:** Survival (PvP 🗡️)

---

## ⚡ Szybkie informacje

| | |
|---|---|
| 🖥️ **IP serwera** | `79.76.97.43` |
| 🎮 **Wersja** | 1.21.7 (kompatybilny wstecz przez ViaVersion) |
| 🧩 **Oprogramowanie** | Purpur (fork Paper) |
| 🎯 **Tryb gry** | Survival — PvP włączone |
| 🟢 **Poziom trudności** | Łatwy |
| 🌍 **Granica świata** | ±2000 bloków |
| 🚫 **Wymiary** | Tylko Overworld (Nether/End wyłączone) |
| 👥 **Maks. graczy** | 20 |
| 📍 **Kraj** | Tylko Polska |
| 🛡️ **Uwierzytelnianie** | AuthMe (tryb offline) |
| 🗺️ **Mapa WWW** | BlueMap (live 3D) |

---

## 📋 Spis treści

- [Informacje o serwerze](#-szybkie-informacje)
- [Jak zacząć?](#-jak-zacząć)
- [Komendy](#-komendy)
- [Wydarzenia](developers/events.md)
- [Dokumentacja developerska](#-dokumentacja-developerska)
- [Szybkie fakty](#-szybkie-fakty)

---

## 🚀 Jak zacząć?

| Krok | Opis |
|---|---|
| 1️⃣ | Dodaj serwer: **`minecraft.reaperq.pl`** (port domyślny) |
| 2️⃣ | Zarejestruj się: `/register <hasło> <hasło>` |
| 3️⃣ | Zaloguj się przy kolejnych wizytach: `/login <hasło>` |
| 4️⃣ | Weź zestaw startowy: `/kit tools` |
| 5️⃣ | Znajdź miejsce na bazę i ustaw dom: `/sethome` |

---

## 🎮 Komendy

| Komenda | Działanie |
|---|---|
| `/home` / `/sethome` | Teleportacja do twojego domu |
| `/tpa <gracz>` | Wyślij prośbę o teleportację |
| `/spawn` | Powrót do spawnu |
| `/back` | Powrót do ostatniego miejsca śmierci |
| `/kit tools` | Zestaw startowy narzędzi |
| `/msg <gracz> <tekst>` | Prywatna wiadomość |
| `/rules` | Zasady serwera |
| `/mail send <gracz> <tekst>` | Wiadomość offline |
| `/list` | Gracze online |

> Pełna lista komend w [dokumentacji](developers/main.md#6-przegląd-komend).

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
| [`developers/events.md`](developers/events.md) | 🎪 Wydarzenia na serwerze |

### Struktura repozytorium

```
minecraft-server/
├── README.md
└── developers/
    ├── main.md       — Architektura i przegląd
    ├── plugins.md    — Dokumentacja pluginów
    ├── modes.md      — Tryby gry
    ├── rules.md      — Zasady i regulamin
    ├── spawn.md      — Spawn i granica świata
    └── events.md     — Wydarzenia
```

---

## 🔍 Szybkie fakty

| Fakt | Szczegóły |
|---|---|
| 🗺️ **Seed świata** | Losowy (ukryty przed graczami) |
| 🔨 **Pre-generacja** | Chunky — promień 2000 |
| 🛡️ **Ochrona spawnu** | 50 bloków |
| ⛏️ **Anti-Xray** | Włączony (tryb 2) |
| 🚫 **VPN/Proxy** | Zablokowane |
| 📦 **Kopie zapasowe** | Codziennie 06:00 GMT, 7 dni wstecz |
| 🧹 **Anty-grief** | CoreProtect + EssentialsXProtect |
| ⚔️ **Combat tag** | 10 sekund |
| 🛌 **Pomijanie nocy** | 1 gracz wystarczy (BetterSleeping) |
| 🤖 **Czat z Discordem** | DiscordSRV (wkrótce) |

---

> 🧱 Survival · PvP · Polska 🇵🇱
