# CatppuccinMocha — Rainmeter Theme

A clean desktop suite for Rainmeter styled with the **Catppuccin Mocha** dark color palette. Six independent skins covering clock, system stats, storage, memory, now playing and weather.

---

## Preview

| Skin | Accent |
|---|---|
| Clock | Mauve `#CBA6F7` |
| Processor | Maroon `#EBA0AC` |
| Storage | Peach `#FAB387` |
| Memory | Lavender `#B4BEFE` |
| Now Playing | Green `#A6E3A1` |
| Weather | Blue `#89B4FA` |

---

## Requirements

| Requirement | Notes |
|---|---|
| **Rainmeter 4.5+** | https://www.rainmeter.net |
| **JetBrains Mono** font | https://www.jetbrains.com/legalnotice/fonts/ — install before loading skins |
| **WebNowPlaying browser extension** | Required for Now Playing skin only — see setup below |

---

## Installation

### 1. Copy skin files

Copy the entire `CatppuccinMocha` folder to your Rainmeter skins directory:

```
%USERPROFILE%\Documents\Rainmeter\Skins\
```

The final path for each skin should look like:
```
Documents\Rainmeter\Skins\CatppuccinMocha\Clock\Clock\Clock.ini
Documents\Rainmeter\Skins\CatppuccinMocha\CPU\CPU\CPU.ini
Documents\Rainmeter\Skins\CatppuccinMocha\HardDrive\HardDrive\HardDrive.ini
Documents\Rainmeter\Skins\CatppuccinMocha\Memory\Memory\Memory.ini
Documents\Rainmeter\Skins\CatppuccinMocha\NowPlaying\NowPlaying\NowPlaying.ini
Documents\Rainmeter\Skins\CatppuccinMocha\Weather\Weather\Weather.ini
```

### 2. Install the WebNowPlaying plugin

Copy `WebNowPlaying-x64.dll` from the `Plugins` folder to:

```
%APPDATA%\Rainmeter\Plugins\
```

> If the `Plugins` folder does not exist, create it.

### 3. Load the skins

1. Right-click the Rainmeter tray icon → **Manage**
2. In the **Skins** tab, expand `CatppuccinMocha`
3. Double-click each skin to load it, or click **Load** on the right panel

---

## Skin Reference

### Clock

Displays the current time in `HH:MM:SS` format with the full date below.

- Updates every **1 second**
- No configuration needed

---

### Processor (CPU)

Shows overall CPU usage as a donut ring with per-core bars and a scrolling history graph.

- Updates every **1 second**
- Shows up to **8 cores** — extra core bars simply read 0 if your CPU has fewer
- Frequency is read from the Windows registry (`~MHz`)
- **CPU temperature** is not shown — this requires a third-party plugin (HWiNFO)

---

### Storage (HardDrive)

Shows used/free space and usage percentage for up to **2 drives**.

**Configuration** — open `HardDrive\HardDrive\HardDrive.ini` and edit:

```ini
[Variables]
Drive1=C:
Drive2=G:
```

Change `Drive2` to any drive letter on your system. Updates every **5 seconds**.

---

### Memory

Shows RAM usage as a donut ring, plus used/free values in GB and a page file bar.

- Updates every **1 second**
- Total installed RAM shown at the bottom
- Page file bar uses `SwapMemory` measure

---

### Now Playing

Shows the currently playing track from Spotify or any media player, with album art, progress bar and playback controls.

#### Setup (required)

The skin uses the **WebNowPlaying** plugin which communicates with a browser extension via WebSocket.

**Step 1 — Install the browser extension:**

| Browser | Link |
|---|---|
| Chrome / Edge | Search "WebNowPlaying Companion" in the Chrome Web Store |
| Firefox | Search "WebNowPlaying" on addons.mozilla.org |

**Step 2 — Play something in Spotify**, then right-click the skin → **Refresh skin**.

The extension icon in your browser toolbar shows a **green dot** when connected.

#### Controls

| Button | Action |
|---|---|
| `\|<` | Previous track |
| `\|\|` | Play / Pause |
| `>\|` | Next track |

#### Supported players

Spotify, YouTube (in browser), SoundCloud, Tidal, Apple Music (web), and most other browser-based players. Also works with the Spotify desktop app when the browser extension is running.

---

### Weather

Shows current temperature, condition, humidity, wind speed and feels-like temperature, fetched automatically based on your location.

**Data sources — no API key required:**
- Location: coordinates set manually in the skin file
- Weather: [open-meteo.com](https://open-meteo.com) — free, open source, no registration

#### Set your location

Open `Weather\Weather\Weather.ini` and edit the three variables at the top:

```ini
[Variables]
Lat=55.604980
Lon=13.003822
CityName=Malmo
```

Find your coordinates at **https://www.latlong.net** — search your city and copy the latitude and longitude.

> **Important:** `Weather.ini` is encoded as **UTF-16 LE** to support the Unicode weather icons (☀ ⛅ ☁ ☂ ❄ ⚡). If you edit this file, use **Notepad++** and ensure the encoding stays as `UTF-16 LE BOM`. Do not re-save with regular Notepad or as UTF-8.

#### Weather icons

| Icon | Condition |
|---|---|
| ☀ | Clear / Mainly clear |
| ⛅ | Partly cloudy |
| ☁ | Overcast / Fog |
| ☂ | Drizzle / Rain / Showers |
| ❄ | Snow |
| ⚡ | Thunderstorm |

Updates every **30 minutes**.

---

## Color Palette

All colors use **Catppuccin Mocha**:

| Role | Name | RGB |
|---|---|---|
| Background | Base | `30, 30, 46` |
| Panel border | Surface1 | `69, 71, 90` |
| Bar track | Surface0 | `49, 50, 68` |
| Primary text | Text | `205, 214, 244` |
| Secondary text | Subtext1 | `186, 194, 222` |
| Muted text | Overlay0 | `108, 112, 134` |
| Clock accent | Mauve | `203, 166, 247` |
| CPU accent | Maroon | `235, 160, 172` |
| Storage accent | Peach | `250, 179, 135` |
| Memory accent | Lavender | `180, 190, 254` |
| Music accent | Green | `166, 227, 161` |
| Weather accent | Blue | `137, 180, 250` |

Full palette reference: https://github.com/catppuccin/catppuccin

---

## File Structure

```
CatppuccinMocha/
├── Clock/
│   └── Clock/
│       └── Clock.ini
├── CPU/
│   └── CPU/
│       └── CPU.ini
├── HardDrive/
│   └── HardDrive/
│       └── HardDrive.ini
├── Memory/
│   └── Memory/
│       └── Memory.ini
├── NowPlaying/
│   └── NowPlaying/
│       └── NowPlaying.ini
├── Weather/
│   └── Weather/
│       └── Weather.ini
├── Plugins/
│   └── WebNowPlaying-x64.dll
└── README.md
```

---

## Troubleshooting

**Skin shows garbled characters like `â°`**
The Weather.ini encoding has been corrupted. Re-copy the original `Weather.ini` file — do not re-save it as UTF-8 or ANSI.

**Now Playing shows "Nothing playing" even when Spotify is running**
- Confirm the browser extension is installed and enabled
- Check the extension icon shows a green dot
- Try right-clicking the skin → Refresh skin
- Make sure you are using the Spotify **desktop app** or **web player in a browser with the extension**

**Weather shows no data**
- Verify your `Lat` and `Lon` values are correct decimals (e.g. `55.604980`, not `55,604980`)
- Open Rainmeter → **About** → **Log** tab to see any WebParser errors
- The skin fetches on load then every 30 minutes — wait a moment after refreshing

**CPU/Memory ring is the wrong color**
Refresh the skin. The ring color is set dynamically on the first update cycle.

**Fonts look wrong**
Make sure **JetBrains Mono** is installed system-wide before loading any skins. Download from https://www.jetbrains.com/legalnotice/fonts/

---

## Credits

- Color palette: [Catppuccin](https://github.com/catppuccin/catppuccin) by the Catppuccin organization (MIT)
- Weather data: [Open-Meteo](https://open-meteo.com) (CC BY 4.0)
- Now Playing plugin: [WebNowPlaying](https://github.com/keifufu/WebNowPlaying-Rainmeter) by keifufu (MIT)
- Font: [JetBrains Mono](https://www.jetbrains.com/legalnotice/fonts/) by JetBrains (OFL)
