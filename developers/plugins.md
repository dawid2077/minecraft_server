# Plugin Index

> Complete list of all plugins installed on the server, with descriptions, features, and relevant configuration notes.

---

## Gameplay & Core

### EssentialsX (2.22.0)

The backbone of the server's gameplay features. Provides the command ecosystem that players interact with daily.

**Modules installed:**
- **EssentialsX** — Core commands: homes, warps, kits, teleportation, messaging, mail
- **EssentialsXChat** — Chat formatting with colors and placeholders
- **EssentialsXSpawn** — Spawn point management
- **EssentialsXProtect** — Anti-grief protections (block placement logging, restricted areas)

**Key features:**
- `/home` / `/sethome` — Set and teleport to personal homes
- `/tpa` / `/tpahere` / `/tpaccept` / `/tpdeny` — Teleport request system
- `/spawn` — Teleport to world spawn
- `/kit tools` — Starter tool kit (delay: 10s)
- `/back` — Return to last death location
- `/msg` / `/reply` — Private messaging
- `/mail` — Offline messaging
- `/rules` — Display server rules
- `/motd` — Server welcome message

---

### VeinMiner (2.4.0)

Allows efficient mining of entire ore veins with a single break. Activated by sneaking while mining.

- **Activation:** Sneak (configurable)
- **Pattern:** Default vein-mining pattern (connected blocks of the same type)
- **Max vein size:** 64 blocks
- **Experience & items:** Collected at source position
- **Disabled game modes:** Creative, Spectator
- **Hunger modifier:** Each block costs 2.5 food saturation

---

### BetterSleeping (1.5)

Improves the night-skipping mechanic. Only **1 player** needs to sleep to skip the night, making it practical for small player counts.

- **Players needed to sleep:** 1
- Works for any number of online players

---

### SimpleScore (4.2.0)

Customizable scoreboard displayed on the right side of the player's screen.

- **Update frequency:** Every tick (20x/second)
- **Async processing:** Enabled (avoids lag)
- **Multi-world support:** Different scoreboards can be configured per world/regex pattern

---

### TAB (6.1.0)

Customizes the player tab list (pressing TAB) with grouping, sorting, and formatted names.

- Player name formatting and prefix/suffix display
- Group-based sorting
- Header/footer customization
- (Configuration is managed server-side — no client mod required)

---

## Security & Enforcement

### AuthMe (6.0.0)

Handles player authentication for the offline-mode server.

- Players must register with a password on first join
- Subsequent logins require the password within a timeout
- Protects against unauthorized access on an unauthenticated server

---

### GrimAC (2.3.74)

Anti-cheat plugin that detects and blocks unfair advantages.

- **Movement checks:** Speed, flight, timer, NoFall, etc.
- **Combat checks:** KillAura, Reach, AutoClicker
- **Experimental checks:** Enabled
- **Setbacks:** Aggressive — players caught cheating are reverted to a safe position quickly

---

### CombatLogX (11.7.0)

Prevents players from logging out to avoid PvP.

- **Tag duration:** 10 seconds after attacking/receiving damage
- **On combat-log (quit while tagged):** Player is killed (items drop)
- **Pets linked:** Tamed animals' damage is attributed to owner
- **Projectile tracking:** Arrows and projectiles link back to the shooter
- **Ignored projectiles:** Eggs, ender pearls, snowballs

---

### CoreProtect (22.4)

Block-level logging and rollback system.

- Logs all block placements, breaks, and interactions
- Supports rollback of player actions (area or player-specific)
- Lookup tool for inspecting who placed/broke what block
- Essential for anti-grief recovery

---

### EssentialsXProtect (2.22.0)

Additional anti-grief protections bundled with EssentialsX.

- Block placement blacklists
- Explosion protection
- Build permission checks tied to the permission system

---

## Server Management

### LuckPerms (5.5.58)

Advanced permissions management system.

- Group-based permission inheritance
- Context-aware permissions (world, server, etc.)
- Tracks (permission sets that can be applied sequentially)
- Storage: H2 database (local, no external DB required)
- Server context: Global (permissions apply across all worlds)

### Maintenance (5.1.0)

Toggle maintenance mode to block connections during updates or troubleshooting.

- **Toggle:** `/maintenance on` / `/maintenance off`
- **Custom MOTD:** Changes when maintenance is active
- **Kick message:** Customizable disconnect reason
- **Language:** Polish (localized for target audience)

### AdvancedServerList (5.8.0)

Customizes the server list ping response shown in the multiplayer menu.

- Custom MOTD with colors and formatting
- Player count display configuration
- Hover messages on the player count
- Favicon support

### CountryBlock

Geo-restriction plugin.

- **Mode:** Allow (only listed countries can join)
- **Allowed:** Poland (PL)
- **VPN detection:** Enabled — blocks connections from VPNs/proxies
- **Kick message:** Players blocked see a country-restriction message

---

## Utility & Quality of Life

### PlaceholderAPI (2.12.2)

Provides placeholder strings like `%player_name%`, `%online_players%` that other plugins can use in messages, scoreboards, and tab lists.

**Plugins that use PlaceholderAPI on this server:**
- SimpleScore
- TAB
- EssentialsXChat
- DecentHolograms (if configured)

---

### DecentHolograms (2.10.1)

Creates floating text holograms in the world.

- Used for informational displays (spawn info, rules, announcements)
- Supports per-player visibility
- Can use PlaceholderAPI placeholders

---

### SkinsRestorer

Restores player skins in offline mode. Since the server doesn't connect to Mojang's auth servers, this plugin retrieves and applies skins from an alternative source.

---

### spark

Performance profiler and metrics tool.

- CPU profiling
- Entity and tile entity tracking
- TPS (ticks per second) monitoring
- Memory analysis
- Accessible in-game with `/spark`

---

### BlueMap (5.12)

Live 3D web map that renders the world in a browser.

- **Access:** `http://<server-ip>:8100`
- Renders terrain, buildings, and player markers
- Updates in real-time as the world changes
- Version 5.12-paper (compatible with Purpur 1.21.7)

---

### ViaVersion (5.10.0)

Allows clients from different Minecraft versions to connect to the 1.21.7 server.

- Backwards compatible — older clients can join
- Translates protocol between versions seamlessly

---

## World & Environment

### Chunky (1.5.3)

World pre-generation tool that generates chunks without requiring player exploration.

- **Radius:** 2000 blocks (overworld)
- **Dimensions:** Overworld only (Nether/End disabled)
- **Function:** Pre-generates all terrain up to the world border
- **Status check:** `/chunky progress` (server console)
- Runs as a background asynchronous task

---

### UltimateAirdrops (2.1.0)

Periodic airdrop events that spawn supply crates at random locations.

- Drops contain random loot
- Visual effects mark landing zones
- Encourages exploration and competition for resources

---

## Integration & Data

### DiscordSRV

Bridges in-game chat with a Discord channel. (Requires bot token and channel ID configuration — currently pending setup.)
