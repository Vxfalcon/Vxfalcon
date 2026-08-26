# TrueSight — Minecraft Developer

I build server-side tooling for Minecraft: anti-cheat systems, custom plugins, and the internal tools that go with running a real server.

## What I work on

**MC Forge** — a desktop tool for building custom Minecraft items end-to-end. Import a Blockbench model, wire up abilities from a library of 100+ built-in effect presets (damage, crowd control, mobility, summons, full custom Java) via a live-previewed builder, configure crafting recipes and NBT data, and export a ready-to-drop Paper plugin plus matching resource pack. Actively developed. *Commercial — not open source.*

**Falconia Anticheat** *(private, discontinued)* — a dual-layer anti-cheat built for the Falconia Factions server: a custom Fabric client mod ("Truesight") paired with server-side enforcement.
- Client mod inspects the active mod folder, loaded class names, classpaths, and mixin configs, and hashes every loaded JAR (SHA-256) against known-good references
- Live string pulling rather than a startup-only snapshot, so anything loaded mid-session still gets caught
- Server-side handshake — a player without the anticheat client installed simply can't connect
- Independent server-side movement/flight checks as a second layer, so the client mod being bypassed isn't enough on its own
- A full web admin panel (Node, Vite, Postgres) for reviewing captured data: mixin config viewer, JAR hash reports, texture pack checker, and a "diff against known-good client" view — plus an integrated Discord bot controller for server management
- Shipped with support for Minecraft 1.21.1–1.21.11, obfuscated for distribution
- Discontinued after a security incident on my machine cost me access to the project

**Plugins** *(private)* — a working collection of Minecraft server plugins and supporting dev tools.

## Stack

![Java](https://img.shields.io/badge/Java-ED8B00?style=flat-square&logo=openjdk&logoColor=white)
![Fabric](https://img.shields.io/badge/Fabric-3B3B3B?style=flat-square&logo=minecraft&logoColor=white)
![Paper/Spigot](https://img.shields.io/badge/Paper%2FSpigot-2C2D72?style=flat-square&logo=minecraft&logoColor=white)
![Node.js](https://img.shields.io/badge/Node.js-339933?style=flat-square&logo=node.js&logoColor=white)
![Electron](https://img.shields.io/badge/Electron-191970?style=flat-square&logo=electron&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white)
