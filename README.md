# Serwer Minecraft

> Prywatny serwer survivalowy działający na Purpur 1.21.7 na Oracle Cloud (aarch64).

## Szybkie linki

| Dokument | Opis |
|---|---|
| [`developers/main.md`](developers/main.md) | Przegląd serwera — architektura, konfiguracja |
| [`developers/plugins.md`](developers/plugins.md) | Pełny indeks pluginów z opisami i funkcjami |
| [`developers/modes.md`](developers/modes.md) | Tryby gry i jak działają |
| [`developers/rules.md`](developers/rules.md) | Zasady serwera |
| [`developers/spawn.md`](developers/spawn.md) | Obszar spawnu, ochrona barierą i granica świata |

## Struktura repozytorium

```
minecraft-server/
├── README.md             ← Jesteś tutaj
├── developers/
│   ├── main.md           — Architektura i przegląd
│   ├── plugins.md        — Dokumentacja pluginów
│   ├── modes.md          — Tryby gry
│   ├── rules.md          — Zasady i regulamin
│   └── spawn.md          — Spawn i granica świata
```

## Szybkie fakty

- **Oprogramowanie:** [Purpur](https://purpurmc.org/) 1.21.7
- **Tryb gry:** Survival (PvP włączone)
- **Poziom trudności:** Łatwy
- **Granica świata:** ±2000 bloków we wszystkich kierunkach
- **Wymiary:** Tylko Overworld (Nether/End wyłączone)
- **Uwierzytelnianie:** Tryb offline z AuthMe
- **Anty-grief:** CoreProtect + EssentialsXProtect
- **Mapa WWW:** BlueMap (live 3D)
- **Gracze:** Maks. 20
