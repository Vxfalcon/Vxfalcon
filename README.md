# TrueSight — Minecraft Developer

I build server-side Minecraft systems end-to-end — anti-cheat, economy and event frameworks, class/ability RPG mechanics, custom items and resource packs, and the tooling that ties it all together.

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

**MoneySMP (recreation)** *(private)* — Money SMP is [a real, existing series](https://moneysmp.fandom.com/wiki/Money_SMP_Wiki); I didn't design the original, this is a from-scratch recreation of its server systems, reimplemented independently as Truesight / Vx.Falcon.
- **Random Events** — recreated the series' signature system: unpredictable events fire throughout a season and run for a set duration (2 hours in recent seasons), layered on top of the daily team games. Implemented events include *Natural Disasters* (last team standing wins), *VIP Protection* (each team guards an assigned VIP while hunting the other's, battle-royale style — last VIP standing wins), and *Double Dough* (kill payouts doubled for the event's duration)
- **Daily/season game modes** — Capture the Flag, King of the Hill, Capture Points (hold a zone for several minutes to bank a payout), Egg Hunt (collectibles scattered for small rewards), Battle Royale finales, and a generic ranked-event mode with configurable payouts and a "gladiator pairs" bracket format
- **Server framework** — player economy (balances, pay, SQLite-backed auction house, leaderboard) and a team + tier system behind it all
- **Custom items & resource pack** — a full custom item set (modern 1.21.4+ component-based item models, not legacy CustomModelData overrides) built for the server's team system
- Death/respawn protection with combat tagging, so freshly-spawned players can't be farmed but raid mechanics still work for staff-judged exceptions

**Alter** *(private)* — a revival-altar / limited-lives plugin: run out of lives and it's not an instant permadeath, it's a ritual other players can actually attempt to save you from.
- Players start with a configurable pool of lives (starting/max/"legendary" tiers); running out is consequential but recoverable
- Death turns the player's head into a revival focus — it can be retrieved and placed inside a staff-defined altar zone (corner-marked bounding box + center block)
- Placing it starts a timed ritual: the head floats and slowly rotates while players hold the zone, with progress broadcasts at intervals — leave the zone empty and the ritual cancels, dropping the head back out
- ProtocolLib drives the floating/rotating head effect; a PlaceholderAPI integration surfaces lives as hearts in other plugins' scoreboards/tab lists
- Also carries a small class-ability layer (Berserker, Executioner, Poseidon, Titan) — a separate experiment in per-player passive/ultimate abilities, independent of the MoneySMP recreation

## Stack

![Java](https://img.shields.io/badge/Java-ED8B00?style=flat-square&logo=openjdk&logoColor=white)
![Fabric](https://img.shields.io/badge/Fabric-3B3B3B?style=flat-square&logo=minecraft&logoColor=white)
![Paper/Spigot](https://img.shields.io/badge/Paper%2FSpigot-2C2D72?style=flat-square&logo=minecraft&logoColor=white)
![ProtocolLib](https://img.shields.io/badge/ProtocolLib-3B3B3B?style=flat-square&logo=minecraft&logoColor=white)
![PlaceholderAPI](https://img.shields.io/badge/PlaceholderAPI-3B3B3B?style=flat-square&logo=minecraft&logoColor=white)
![Node.js](https://img.shields.io/badge/Node.js-339933?style=flat-square&logo=node.js&logoColor=white)
![Electron](https://img.shields.io/badge/Electron-191970?style=flat-square&logo=electron&logoColor=white)
![SQLite](https://img.shields.io/badge/SQLite-003B57?style=flat-square&logo=sqlite&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white)
