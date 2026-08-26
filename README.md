# TrueSight — Minecraft Developer

I build server-side tooling for Minecraft: anti-cheat systems, custom plugins, and the internal tools that go with running a real server.

## What I work on

**MC Forge** — a desktop tool for building custom Minecraft items end-to-end. Import a Blockbench model, wire up abilities from a library of 100+ built-in effect presets (damage, crowd control, mobility, summons, full custom Java) via a live-previewed builder, configure crafting recipes and NBT data, and export a ready-to-drop Paper plugin plus matching resource pack. Actively developed. *Commercial — not open source.*

**Falconia Anticheat** *(private, discontinued)* — a manual-inspection anti-cheat built for the Falconia Factions server: a required Fabric client mod ("Truesight") that reports into a self-hostable admin panel, so staff can actually look at what's running on a suspicious player's machine instead of trusting a black-box verdict.
- Server-side handshake — a player without the client mod installed simply can't connect
- The panel surfaces the active mod folder, loaded class names, classpaths, and mixin configs, live rather than as a one-time startup snapshot
- Every loaded JAR gets SHA-256 hashed for admins to compare against known-good references, alongside a texture pack checker and a "diff against known-good client" view
- Independent server-side movement/flight checks run alongside it, so a compromised or bypassed client mod isn't the only line of defense
- Web admin panel built on Node, Vite, and Postgres, with an integrated Discord bot controller for server management
- Shipped with support for Minecraft 1.21.1–1.21.11, obfuscated for distribution
- Discontinued after a security incident on my machine cost me access to the project

**MoneySMP** *(private)* — built as Truesight / Vx.Falcon — a complete custom SMP server build: economy, live-run events, a full RPG-style ability system, and a matching resource pack, all built and maintained together.
- **Server framework** — player economy (balances, pay, SQLite-backed auction house, leaderboard), a team + tier system, and eight built-in event modes: Capture the Flag, King of the Hill, Control Points, Egg Hunt, Battle Royale, Natural Disasters, VIP Protection, and generic ranked events with payouts
- **Ability system** — 11 mythology-themed classes (Poseidon, Berserker, Titan, Executioner, Tempest, Inferno, Phantom, Gaia, Chronos, Nyx, Aether), each with a distinct passive and a multi-stage ultimate (windup → payoff, with matching particle/sound feedback), a charge-based cooldown economy per ability, a paid random-reroll system, and an anti-kill-farm safeguard so charge-farming the same victim repeatedly doesn't pay out
- **Custom items & resource pack** — a full custom item set (modern 1.21.4+ component-based item models, not legacy CustomModelData overrides) built for the server's team system, plus custom items woven through the plugins themselves (reroll costs, totem tasks, banned-item rules)
- Death/respawn protection with combat tagging, so freshly-spawned players can't be farmed but raid mechanics still work for staff-judged exceptions

## Stack

![Java](https://img.shields.io/badge/Java-ED8B00?style=flat-square&logo=openjdk&logoColor=white)
![Fabric](https://img.shields.io/badge/Fabric-3B3B3B?style=flat-square&logo=minecraft&logoColor=white)
![Paper/Spigot](https://img.shields.io/badge/Paper%2FSpigot-2C2D72?style=flat-square&logo=minecraft&logoColor=white)
![Node.js](https://img.shields.io/badge/Node.js-339933?style=flat-square&logo=node.js&logoColor=white)
![Electron](https://img.shields.io/badge/Electron-191970?style=flat-square&logo=electron&logoColor=white)
![SQLite](https://img.shields.io/badge/SQLite-003B57?style=flat-square&logo=sqlite&logoColor=white)
