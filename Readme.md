# SIGNAL IPTV Player

SIGNAL is a local IPTV player for M3U and HLS playlists.
It runs as a single HTML file directly in the browser and supports EPG data in XMLTV format.

![Preview](./images_/preview.jpg)

## Features

- Playback of M3U and M3U8/HLS playlists
- Playlist import via URL or file
- EPG support via XMLTV URL or XML/XML.GZ file
- Favorites list
- Rename or hide categories
- Program guide with search
- Audio and subtitle track selection, if offered by the stream
- Multi-language UI (dropdown in the header) — English by default, with more languages easy to add
- Local storage of playlists, favorites, and settings (backup export/import)
- Optional local proxy for servers with CORS restrictions
- No external CDNs, fonts, or tracking services

## Usage

1. Download `iptv_player.html`.
2. Open the file in your browser.
3. Add a playlist via URL or file.
4. Select a channel and play it.
5. Optionally add an EPG source to the playlist.

## Language

The UI language can be switched via the dropdown in the top-right header (default: English).
The chosen language is remembered for future visits. Additional languages can be added by
extending the `AVAILABLE_LANGS` list and the corresponding translation dictionary in the file.

## Local Storage

SIGNAL stores its configuration locally in the browser.
In supported browsers, a folder can additionally be linked. The file `signal-config.json` is
created there and updated automatically.

Stored data includes:

- Playlists
- Favorites
- Category customizations
- Settings
- Last-watched channel
- EPG sources

## EPG and CORS

Some EPG or playlist servers block direct browser requests due to CORS restrictions.
Three built-in options are available:

1. The URL works directly and there is no CORS issue.
2. The URL doesn't work directly, so a public CORS proxy is used as a fallback — but only if the local Python proxy isn't running.
3. A local (Python) proxy running at `127.0.0.1:8787`. This takes priority over the public proxy in option 2.

> The Python proxy script can be downloaded from the settings (gear icon, top right) as a standalone `.py` file.

---

# License

This project is licensed under a custom, non-commercial license — see LICENSE. Non-commercial use,
copying, and modification are permitted; commercial use requires prior written permission from the author.

Disclaimer: This software is provided "as is". No liability is assumed for data loss or security
incidents. Use at your own risk.
