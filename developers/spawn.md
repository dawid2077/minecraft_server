# Spawn Area & World Border

> Documentation on the spawn protection zone, world border, and how the world is configured for survival.

---

## 1. Spawn Area

The spawn is the central hub where all players appear on first join or when using `/spawn`.

### Spawn Protection

- **Protection radius:** 50 blocks from world spawn (0, 0)
- **Who can build:** Only operators with `essentials.protect` or equivalent permission
- **What's protected:** Block breaking, block placement, interactions with containers
- **Purpose:** Prevent spawn griefing and preserve the spawn area for community use

### Spawn Features

| Feature | Details |
|---|---|
| **Spawn point** | World spawn at (0, ~64, 0) |
| **Community builds** | Spawn area is reserved for community infrastructure |
| **Information** | Holograms at spawn display rules and info for new players |
| **Spawn on join** | Disabled (players spawn at their last logout location) |
| **Spawn on death** | Standard — players respawn at world spawn |

### Teleport Commands

| Command | Behavior |
|---|---|
| `/spawn` | Teleports you to world spawn |
| `/sethome` | Set a personal home point (use this at your base) |
| `/home` | Teleport to your personal home |
| `/back` | Return to your last death location |

---

## 2. World Border

The world is bounded by a **hard border** at ±2000 blocks on both the X and Z axes.

### What This Means

- The playable area is a 4000×4000 block square centered on (0, 0)
- Players cannot walk, fly, or teleport past the border
- Any build, exploration, or activity must happen within this area

### Why a Border?

- Server resources: Smaller world = smaller disk usage, faster backups, less memory
- Player density: Keeps players closer together for a more social experience
- Resource management: Easy to pre-generate the full world with Chunky

---

## 3. World Pre-generation

All chunks within the border are pre-generated to ensure smooth gameplay.

| Detail | Value |
|---|---|
| **Tool** | Chunky |
| **Radius** | 2000 blocks |
| **Dimensions** | Overworld only |
| **Status** | Background task (players can play during generation) |

Pre-generation means:
- No chunk-loading lag when exploring new areas
- Terrain, caves, and structures are already calculated
- Anti-Xray is effective immediately in all areas

---

## 4. World Configuration Summary

| Setting | Value |
|---|---|
| **Border radius** | 2000 blocks |
| **Border center** | (0, 0) — world spawn |
| **Spawn radius** | 50 blocks protected |
| **View distance** | Default |
| **Monster spawns** | Enabled (Easy difficulty) |
| **Animal spawns** | Enabled |
| **Anti-Xray** | Engine mode 2 (hides ores) |
| **Nether** | Disabled |
| **End** | Disabled |
| **World seed** | Random (hidden from players) |

---

## 5. Visiting Other Areas

### Using `/tpa` to Visit Other Players

The teleport request system allows players to visit each other's bases:

1. Request: `/tpa <playername>`
2. Target accepts: `/tpaccept <playername>`
3. You teleport to their location

### Using `/home` to Return to Your Base

1. Set your base: `/sethome` (at your chosen location)
2. Return anytime: `/home`

---

## 6. Map

A live 3D web map is available via BlueMap. It renders the entire world and updates in real-time.

**Features:**
- See builds, terrain, and player locations on the map
- Navigate the world from a bird's-eye view
- Useful for finding landmarks and planning exploration routes
