# Catppuccin Rainmeter

A clean desktop widget suite for [Rainmeter](https://www.rainmeter.net) styled with the [Catppuccin](https://github.com/catppuccin/catppuccin) color palette. Includes all four flavors — **Mocha**, **Macchiato**, **Frappé**, and **Latte** — each with six independent skins.

---

## Skins

| Skin | Description | Accent |
|---|---|---|
| **Clock** | Time in `HH:MM:SS` with full date | Mauve |
| **Processor (CPU)** | Overall usage donut, per-core bars, history graph | Maroon |
| **Storage (HardDrive)** | Used/free space for up to 2 drives | Peach |
| **Memory** | RAM usage donut, used/free in GB, page file bar | Lavender |
| **Now Playing** | Track info, album art, progress bar, playback controls | Green |
| **Weather** | Temperature, condition, humidity, wind (via Open-Meteo) | Blue |

---

## Flavors

Each folder is a self-contained Rainmeter skin suite:

- **CatppuccinMocha** — dark, warm tones (see [detailed README](CatppuccinMocha/README.md))
- **CatppuccinMacchiato** — dark, muted tones
- **CatppuccinFrappé** — mid-tone, pastel
- **CatppuccinLatte** — light theme

---

## Requirements

- **Rainmeter 4.5+** — https://www.rainmeter.net
- **JetBrains Mono** font — https://www.jetbrains.com/legalnotice/fonts/
- **WebNowPlaying** browser extension — required for the Now Playing skin only

---

## Installation

1. Copy your preferred flavor folder (e.g. `CatppuccinMocha`) to:
   ```
   %USERPROFILE%\Documents\Rainmeter\Skins\
   ```
2. Copy `WebNowPlaying-x64.dll` from the flavor folder to:
   ```
   %APPDATA%\Rainmeter\Plugins\
   ```
3. Right-click the Rainmeter tray icon → **Manage** → expand the flavor → load each skin.

---

## Configuration

- **Storage** — edit `HardDrive.ini` and set your drive letters in the `[Variables]` section.
- **Weather** — edit `Weather.ini` and set `Lat`, `Lon`, and `CityName`. Find your coordinates at [latlong.net](https://www.latlong.net). Keep the file encoded as **UTF-16 LE** to preserve weather icons.

---

## Credits

- Color palette: [Catppuccin](https://github.com/catppuccin/catppuccin) (MIT)
- Weather data: [Open-Meteo](https://open-meteo.com) (CC BY 4.0)
- Now Playing plugin: [WebNowPlaying](https://github.com/keifufu/WebNowPlaying-Rainmeter) by keifufu (MIT)
- Font: [JetBrains Mono](https://www.jetbrains.com/legalnotice/fonts/) by JetBrains (OFL)
