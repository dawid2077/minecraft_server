# Minecraft Server

> Private survival server running Purpur 1.21.7 on Oracle Cloud (aarch64).

## Quick Links

| Document | Description |
|---|---|
| [`developers/main.md`](developers/main.md) | Server overview — architecture, setup, and architecture |
| [`developers/plugins.md`](developers/plugins.md) | Complete plugin index with descriptions and features |
| [`developers/modes.md`](developers/modes.md) | Game modes and how they work |
| [`developers/rules.md`](developers/rules.md) | Server rules |
| [`developers/spawn.md`](developers/spawn.md) | Spawn area, barrier protection, and world border |

## Repo Structure

```
minecraft-server/
├── README.md             ← You are here
├── developers/
│   ├── main.md           — Architecture & overview
│   ├── plugins.md        — Plugin documentation
│   ├── modes.md          — Game modes
│   ├── rules.md          — Rules & policies
│   └── spawn.md          — Spawn & world border
```

## Quick Facts

- **Software:** [Purpur](https://purpurmc.org/) 1.21.7
- **Gamemode:** Survival (PvP enabled)
- **Difficulty:** Easy
- **World border:** ±2000 blocks in all directions
- **Dimensions:** Overworld only (Nether/End disabled)
- **Authentication:** Offline mode with AuthMe
- **Anti-grief:** CoreProtect + EssentialsXProtect
- **Web map:** BlueMap (live 3D)
- **Players:** 20 max
