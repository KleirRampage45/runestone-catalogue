# Runestone Game Catalogue

A curated catalogue of free games for the [Runestone](https://github.com/KleirRampage45/Runestone) Android game launcher — supporting RPG Maker (2000/2003/XP/VX/VX Ace/MV/MZ), Ren'Py, Godot, ONScripter, TyranoBuilder, and WebView-based engines.

**Live URL:**  
```
https://raw.githubusercontent.com/KleirRampage45/runestone-catalogue/main/games.json
```

---

## How to Use

1. Open Runestone
2. Tap the **STORE** icon in the dock
3. Tap the **CFG** button → **Provider Settings**
4. Tap **Use Public Catalogue** (pastes the URL above automatically) or paste it manually
5. Go back — games will appear in the Store tab
6. Tap a game to see download options, then download & install

---

## How to Contribute

Open a pull request to add or update games in `games.json`. Each entry follows this schema:

### Game Entry Format

```json
{
  "id": "fear-and-hunger",
  "title": "Fear and Hunger",
  "engine": "rgss_vx_ace",
  "fileSize": 831830000,
  "downloadOptions": [
    {
      "name": "Pixeldrain",
      "host": "Pixeldrain",
      "url": "https://pixeldrain.com/u/eVEBFSXX",
      "fileSize": 831830000
    }
  ],
  "sourceName": "steamgg"
}
```

| Field | Required | Description |
|-------|----------|-------------|
| `id` | ✅ | URL-safe unique identifier (kebab-case, e.g. `fear-and-hunger-2`) |
| `title` | ✅ | Display title |
| `engine` | ✅ | One of the supported engines (see table below) |
| `fileSize` | ❌ | Game size in bytes. `null` if unknown |
| `downloadOptions` | ✅ | Array of download mirrors (at least 1) |
| `downloadOptions[].name` | ✅ | Short label for the mirror (e.g. `Pixeldrain`, `Mediafire`) |
| `downloadOptions[].host` | ✅ | Hoster name (same as `name`) |
| `downloadOptions[].url` | ✅ | Direct download URL to a `.zip` or `.rar` file |
| `downloadOptions[].fileSize` | ❌ | Size of this specific download in bytes |
| `sourceName` | ❌ | Where the game was sourced from (e.g. `steamgg`, `vgperson`, `itchio`) |

### Supported Engines

| engine value | Engine | Runestone Runtime | Verified? |
|-------------|--------|-------------------|-----------|
| `easyrpg` | RPG Maker 2000 / 2003 | EasyRPG Player | ✅ |
| `rgss_xp` | RPG Maker XP | mkxp-z | ✅ |
| `rgss_vx` | RPG Maker VX | mkxp-z | ✅ |
| `rgss_vx_ace` | RPG Maker VX Ace | mkxp-z | ✅ |
| `rpgmakermv` | RPG Maker MV | WebView (system browser) | ✅ |
| `rpgmakermz` | RPG Maker MZ | WebView (system browser) | ✅ |
| `renpy` | Ren'Py | Native (wrapper in development) | ⚠️ Partial |
| `godot` | Godot Engine | Native (addon, optional) | ✅ |
| `nscripter` | ONScripter/NScripter | libonscripter.so | ✅ |
| `tyranobuilder` | TyranoBuilder | WebView | ✅ |
| `html` | Generic HTML5 game | WebView | ✅ |
| `twine` | Twine / Harlowe / Sugarcube | WebView | ✅ |
| `ruffle` | Flash / SWF | Ruffle.js (CDN) | ✅ |
| `construct` | Construct 2 / 3 | WebView | ✅ |

### Rules for Contribution

#### ✅ DO
- **Verify the engine before adding.** Many 2D pixel-art games are Unity or Unreal, NOT RPG Maker. Check on [PCGamingWiki](https://www.pcgamingwiki.com), [Wikipedia](https://en.wikipedia.org), [SteamDB](https://steamdb.info), or the developer's site before assigning an engine.
- **Use working download hosters.** Runestone can download from these:
  - ✅ **Pixeldrain** (`https://pixeldrain.com/u/...`) — works on Android, preferred
  - ✅ **Datanodes** — works on Android
  - ✅ **Rootz.so** — works on Android
  - ✅ **Gofile** — works if link resolves to a direct file
  - ✅ **Akirabox** — works on Android
  - ❌ **Mediafire** — Android downloads are broken (mobile UA gets no CDN links)
  - ❌ **MEGA / 1Fichier** — not supported by Runestone's downloader
  - ❌ **Torrent / Magnet links** — not supported
- **Provide multiple mirrors** if the same game is available on different hosters.
- **Single games only.** Bundles containing multiple games won't work — Runestone downloads a single archive and detects one engine from it.
- **Make sure the download is a direct `.zip` / `.rar` / `.7z` file**, not a store page or redirect page.
- **Test the download URL** before submitting a PR.

#### ❌ DON'T
- **Don't guess engines.** If you're not 100% sure what engine a game uses, search for it first.
- **Don't add AAA/pirated games.** Only freeware, indie, or otherwise freely distributable games.
- **Don't add bundles.** One game = one entry. No "Complete Collection" or "Series Bundle" entries.
- **Don't add games that need Wine/FEX to run** (native Windows games on Android). Runestone runs native Android runtimes, not an emulation layer.
- **Don't add NSFW content without clearly marking it in the title** with `[18+]` or similar. Runestone is GPLv2+ open source and may be used by all ages.
- **Don't bump the `version` field** — the maintainer will do this when merging.

### Common Engine Traps

These games look like RPG Maker but aren't. **Do NOT mark them as RPG Maker:**

| Game | Looks Like | Actual Engine |
|------|-----------|---------------|
| Ender Lilies / Ender Magnolia | 2D pixel Metroidvania | **Unreal Engine 4/5** |
| Coffee Talk series | 2D pixel VN | **Unity** |
| Alisa | PS1-style survival horror | **Unity** |
| ASTLIBRA Revision | 2D side-scrolling RPG | **Proprietary** |
| Mega Man X DiVE | 2D platformer | **Unity** |
| Momodora: Moonlit Farewell | 2D Metroidvania | **Unity / GameMaker** |
| The Coma: Cutting Class | 2D horror | **Unity** |
| Corpse Party (2021) | Horror adventure | **Unity** (remake) |
| Detention | 2D horror | **Unity** |
| Knock on the Coffin Lid | Card-based RPG | **Unity** |
| Doki Doki Literature Club **Plus!** | Visual Novel | **Unity** (original DDLC was Ren'Py, Plus version rebuilt in Unity) |
| The Letter - Horror Visual Novel | Visual Novel | **Unity** |
| Hylics 2 | Weird RPG | **Unity** (Hylics 1 was RPG Maker VX Ace, sequel is Unity) |

When in doubt, search:
- `pcgamingwiki.com/wiki/GAME_TITLE` — look for "Engines"
- `steamdb.info/app/STEAMID/info/` — look for "Engine" field
- Wikipedia article for the game

---

## File Structure

```
runestone-catalogue/
├── README.md          # This file
├── games.json         # The catalogue (consumed by Runestone)
└── CONTRIBUTORS.md    # (optional) List of contributors
```

---

## License

The catalogue itself is public domain ([CC0](https://creativecommons.org/publicdomain/zero/1.0/)).  
Game content belongs to their respective creators.  
Runestone is GPLv2+ — see [the main repo](https://github.com/KleirRampage45/Runestone).
