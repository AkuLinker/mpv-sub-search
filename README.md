# mpv-sub-search
Lua script for mpv. Allows to search subtitles with uosc interface.

![Preview](preview.png)

![Preview](preview.gif)

## Why not the built-in `select-subtitle-line`?
mpv already ships a similar feature (`script-binding select/select-subtitle-line`, default `g-l`). This script exists because that built-in has a couple of issues:
- It splits multi-line subtitle events into separate list entries per visual line, instead of treating each full line as one item. This fragments phrases that wrap across two lines and makes searching them unreliable.
- It has no caching, so it re-extracts and re-parses subtitles via ffmpeg on every menu open.
- It doesn't pauses playback while the menu is open, and has no option to change that.

## Requirements
- **[uosc](https://github.com/tomasklaen/uosc)**
- **[ffmpeg](https://git.ffmpeg.org/ffmpeg.git)**

## Installation
Place `sub-search.lua` in your mpv `scripts` folder.

## Keybindings
No keys are bound by default. Add these to your `input.conf`:
```
<key> script-binding sub-search-open
<key> script-binding sub-search-open-secondary
```
## Usage
Press the bound key — a uosc palette opens with all subtitle lines.
Type words to filter. Click or press Enter on a result to jump to that moment.
