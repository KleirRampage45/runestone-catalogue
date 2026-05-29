# Runestone Game Catalogue

A curated list of free RPG Maker games for the [Runestone](https://github.com/KleirRampage45/Runestone) Android game launcher.

## How to Use

1. Open Runestone
2. Tap the **STORE** icon in the dock
3. Tap **Provider Settings** (CFG button)
4. Paste this URL:
   ```
   https://raw.githubusercontent.com/KleirRampage45/runestone-catalogue/main/games.json
   ```
5. Go back — games will appear!

## Adding Games

Open a pull request to add games to `games.json`. Each entry needs:

| Field | Required | Description |
|-------|----------|-------------|
| `id` | ✅ | Unique identifier |
| `title` | ✅ | Game title |
| `engine` | ✅ | `easyrpg`, `rgss_xp`, `rgss_vx`, `rgss_vx_ace`, `mv`, `mz`, `renpy` |
| `fileSize` | ❌ | Size in bytes |
| `downloadUrl` | ✅ | Direct download link (.zip) |
| `sourceName` | ❌ | Where the game comes from (itch.io, rpgmaker.net, etc.) |
| `coverUrl` | ❌ | Cover/box art URL |

## Rules

- Only **freeware** games (no commercial/pirated content)
- Must be playable in Runestone (RPG Maker XP/VX/VX Ace/MV/MZ, Ren'Py, EasyRPG)
- Direct download links only (no store pages)
- Test that the download URL works before opening a PR

## License

The catalogue itself is public domain. Game content belongs to their respective creators.
