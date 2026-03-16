# Linked Media Player

![TV Source](../images/guition-esp32-p4-jc8012p4a1-tvsource.jpg)

If your speaker has a secondary input — either a **TV source** (soundbars like Sonos Beam or Arc with HDMI) or a **Line In source** (speakers and amps like Sonos Five, Play:5, Port, or Amp with a 3.5mm/RCA input) — the controller can show now-playing info from the media player connected to that input. This feature is entirely optional — the controller works without it.

> [!WARNING]
> This feature is in **beta**. If you encounter any issues, please [open an issue on GitHub](https://github.com/jtenniswood/esphome-media-player/issues).

## How it works

- **Automatic switching** — when the primary media player's source becomes "TV" or "Line In", the UI shows title, artist, artwork, and progress from the linked media player. When the source changes back, the UI reverts to the primary player.
- **Idle state** — when the linked player is idle, off, or on standby, the screen displays the source name ("TV" or "Line In") on a black background with playback controls hidden. Controls reappear when the linked player starts playing again.
- **Routed controls** — play/pause, next, and previous are automatically sent to whichever player is active (music or linked).

## Setup

On the device page in Home Assistant (**Settings → Devices & Services → ESPHome** → your device), set the **Linked Media Player** field to the entity ID of the media player connected to your input (e.g. `media_player.apple_tv`).

Leave this field empty to disable the feature.

## Compatibility

This feature works with any speaker that exposes a "TV" or "Line In" source attribute and any media player entity in Home Assistant.

Tested with:

- **TV source** (soundbars): Sonos Beam, Sonos Arc
- **Line In source** (speakers/amps): Sonos Five, Sonos Play:5, Sonos Amp, Sonos Port
- **Linked media players**: Apple TV, Chromecast
