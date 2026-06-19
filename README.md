# RaidCDSync

A World of Warcraft addon that lets every healer self-report their cooldowns to the group — no combat-log snooping, no raid-leader permissions required.

> **Note:** This repository is for issue tracking and feature requests only. The addon files are distributed via CurseForge / WoWInterface. Download the latest release from there and drop the `RaidCDSync` folder into your `Interface/AddOns/` directory.

---

## What it does

When a ready check fires, each player with RaidCDSync broadcasts a snapshot of their selected spells and ready/on-cooldown state to the whole group over addon messages. Every other healer with the addon picks it up and displays it in a compact tracker window. Live update packets follow each cast and reset, so the display stays current mid-pull — no polling, no guessing.

Only players assigned the **Healer** role in the group are shown in the tracker, keeping it clean for healers-only.

---

## Slash commands

| Command | What it does |
|---|---|
| `/rcd` | Toggle the tracker window |
| `/rcd config` | Open or close the settings window |
| `/rcd snap` | Broadcast your current snapshot to the group |
| `/rcd ready <spellID>` | Force-mark a spell as ready |
| `/rcd used <spellID>` | Force-mark a spell as on cooldown |
| `/rcd minimap` | Show or hide the minimap button |
| `/rcd debug` | Toggle debug output in chat |
| `/rcd reset` | Clear all synced data and reset the display |

---

## Configuration

Open `/rcd config` or click the minimap button to access settings:

- **Spells tab** — choose which healer cooldowns to broadcast. Type a spell ID, a spell name you know, or click the box then shift-click a spell in your spellbook to add a custom spell.
- **Profiles tab** — save and load spell selections as named presets.
- **Appearance tab** — resize and reposition the tracker window, toggle overlay/lock mode.
- **Statistics tab** — see ready-check history and cast counts per spell.
- **About tab** — slash command reference and version info.

---

## Reporting issues & requesting features

Use the [Issues](https://github.com/qusoqt/RaidCDSync/issues) tab on this repository.

When reporting a bug please include:
- Your WoW version and addon version (shown in `/rcd config` → About)
- Steps to reproduce
- What you expected vs. what happened
- Any relevant chat output from `/rcd debug`

Feature requests are welcome — open an issue and tag it **enhancement**.

---

## Compatibility

- **Interface:** 120007 (The War Within / current retail)
- **Sync:** all group members need RaidCDSync for data to flow both ways. Players without it are simply not shown.
- **Custom spells** sync to the group only if both sides have added the same spell ID — packets carry IDs only, not spell names.
