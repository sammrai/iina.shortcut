# Troubleshooting

## Test if IINA Works with YouTube

First, verify that IINA can open YouTube videos with this command:

```bash
open -a IINA "https://www.youtube.com/watch?v=dQw4w9WgXcQ"
```

If the video doesn't open, try the steps below.

## Required Dependencies

Make sure you have the required packages installed:

```bash
brew install socat yt-dlp
```

## If YouTube Videos Won't Play in IINA

IINA sometimes fails to play YouTube videos due to outdated mpv hooks. To update the YouTube playback hook, run these commands:

```bash
mkdir -p ~/.config/mpv/scripts
curl -L https://raw.githubusercontent.com/mpv-player/mpv/master/player/lua/ytdl_hook.lua \
  -o ~/.config/mpv/scripts/ytdl_hook.lua
chmod 644 ~/.config/mpv/scripts/ytdl_hook.lua
```
