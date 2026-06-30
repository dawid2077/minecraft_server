# Server Architecture

> Technical overview of the Minecraft server infrastructure, software stack, and operational notes.

---

## 1. Host & Infrastructure

| Detail | Value |
|---|---|
| **Host type** | VM (arm64/aarch64) |
| **OS** | Oracle Linux 9 |
| **RAM allocated** | 8 GB |
| **CPU cores** | 2 (arm64) |
| **Java** | 21 |
| **Server dir** | `~/minecraft/` |
| **Process manager** | tmux (session: `mc-server`) |

### JVM Flags

The server runs with Aikar's recommended G1GC flags tuned for 2-core ARM. These minimize garbage collection lag spikes.

### Firewall

- **Minecraft port:** TCP+UDP 25565 (firewalld + cloud firewall ingress rules)
- **BlueMap web map:** Port 8100 (firewalld + cloud firewall)

---

## 2. Software Stack

### Server Software

- **[Purpur](https://purpurmc.org/)** 1.21.7 — fork of Paper/Pufferfish with additional configuration options
- **Offline mode:** `online-mode=false` — authentication delegated to AuthMe plugin

### World Settings

- **World border:** ±2000 on X and Z axes (radius 2000 from spawn)
- **Overworld only:** Nether and End dimensions are disabled
- **World seed:** Randomly generated, hidden from players
- **Spawn protection:** Radius 50 blocks (Purpur managed)
- **Anti-Xray:** Engine mode 2 enabled (hides ores as stone in unexposed chunks)

---

## 3. Operational Notes

### World Pre-generation

The world is pre-generated using Chunky at radius 2000. This runs as a background task and does not require server downtime. Players can continue playing while generation runs.

### Backups

- **Schedule:** Daily at 06:00 GMT
- **Retention:** 7 days (automatic cleanup of older backups)
- **Format:** Gzipped tarball
- **Excludes:** Player data files (individual player inventories/positions)
- **Location:** `~/minecraft/backups/`

### Maintenance Mode

The server has a maintenance mode toggle (`/maintenance on` / `/maintenance off`). When active, the MOTD changes to indicate maintenance and new connections are blocked until the mode is disabled.

### Server Start / Stop

- **Start:** Run `~/minecraft/start.sh` (inside tmux)
- **Graceful stop:** Send `stop` command to server console
- **Force stop:** Send `kill` command only if graceful stop fails

---

## 4. Plugin Ecosystem

See [`plugins.md`](plugins.md) for the full plugin index.

Key plugin categories:

| Category | Plugins |
|---|---|
| **Core gameplay** | EssentialsX suite, VeinMiner |
| **Security** | AuthMe, GrimAC, CoreProtect, CombatLogX |
| **Quality of life** | BetterSleeping, SimpleScore, TAB |
| **Server management** | LuckPerms, Maintenance, AdvancedServerList |
| **Web/map** | BlueMap |
| **Cross-version** | ViaVersion |
| **World** | Chunky |

---

## 5. Player Access

- **Authentication:** Players log in via AuthMe password
- **Whitelist:** Not enforced (anyone with correct auth can join after signup)
- **Country restriction:** Server is restricted to Poland only (via CountryBlock) — players from other countries are blocked at connection time
- **VPN detection:** Enabled — players using VPNs/proxies are blocked
- **Max players:** 20

### Known Players

- reaperq
- Whopper_Junior2
- Low_Death_Gaming

---

## 6. Commands Overview

Players have access to a curated command set through LuckPerms, primarily from EssentialsX:

| Command group | Description |
|---|---|
| `/home`, `/sethome` | Personal homes |
| `/tpa`, `/tpahere`, `/tpaccept`, `/tpdeny` | Teleport requests |
| `/spawn` | Return to spawn |
| `/kit` | Starter kits (tools, etc.) |
| `/msg`, `/reply` | Private messaging |
| `/mail` | Offline messaging |
| `/back` | Return to last death location |
| `/list` | Online players |
| `/help` | Command help |
| `/rules` | Server rules |

### Administrative Commands

Admin commands are gated behind LuckPerms permissions. Available to ops/admins:

- `/maintenance` — Toggle maintenance mode
- `/coreprotect` — Block inspection and rollback
- `/lp` — LuckPerms permission management
- `/gamemode` — Change game mode
- `/vanish` — Become invisible
