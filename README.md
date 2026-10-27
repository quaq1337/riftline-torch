# Riftline

A local Windows companion for **Torchlight: Infinite**. Riftline reads the English game screen and local log, calculates advice on your computer, and highlights a recommended choice. You perform every game action yourself.

[**Download the latest Windows installer**](https://github.com/quaq1337/riftline-torch/releases/latest) · [Release history](https://github.com/quaq1337/riftline-torch/releases) · [Changelog](CHANGELOG.md) · [Report an issue](https://github.com/quaq1337/riftline-torch/issues)

## Install

Download `Riftline-<version>-Setup.exe` from the release assets and run it. No manual archive extraction, Python or Node.js installation is needed. Installation uses your Windows account and creates a desktop shortcut. The dashboard starts in the tray; the overlay stays available over the game.

Windows x64 and English game text are supported. Use borderless windowed mode. Recognition follows the game window; unusual UI scales, unsupported layouts or other overlays covering game information can still prevent a reliable reading.

## Mechanics

| Module | Status |
| --- | --- |
| Vorax | Card and target advice, score forecasts, special potion chains, starting instruments, pet settings, available-reroll evaluation and run history. |
| Tartarus | **Preview.** Instrument, board, objective and reward recognition, one highlighted action, and model-based remaining-run Chromatic forecasts when current facts and effects are supported. |

Tartarus is still being validated on independent PCs and complete live runs. Unknown effects or unread state can block advice. Forecasts are estimates under the implemented simulator, not guaranteed rewards or exact optimal play. An unread effect is not silently treated as absent.

## Version 0.3.10

Batch Tartarus recognition, stable accepted input context, bounded diagnostic recordings and revalidated saved-state restart recovery. Vorax behavior is unchanged. Tartarus remains a preview; first-time startup on an arbitrary late board without complete observed state is not yet supported.

## Version 0.3.9

Initial instrument hotfix: separate Tartarus capture from Riftline windows, repair current instrument/title and visible reroll reading, recognize the Doors objective counter, and retain the configured pet profile on screen-based entry. A fully re-read initial choice can recover pre-observation clicks without inventing an acquisition. Tartarus remains a preview; a complete independent live run has not been accepted.

## Version 0.3.8

- Faster complete Tartarus forecasts using bounded parallel work with the original samples and scenario aggregation retained.
- Held-instrument recognition fixes and logged confirmation handling for rapid card selection and subsequent rewards.
- Capture-visible panel and highlights, with a setting to exclude them from supported Windows capture paths.
- A smaller installer that retains OCR models and active runtime dependencies, plus bounded diagnostic storage and obsolete updater-cache cleanup.

The first Tartarus initialization needs an Internet connection to obtain five pinned, integrity-checked simulator resources from their original repository. A verified local cache can be reused offline. No project checkout or another player's settings/history is required.

## Controls and recording

| Control | Action |
| --- | --- |
| F8 / Refresh | Read the game again. |
| Picture | Capture the game directly into recognition. |
| F9 | Pause or resume automatic reading. |
| Close dashboard | Keep Riftline running in the tray. |
| Tray → Exit | Fully close the application. |

For OBS, use **Display Capture**; for Discord, share the **entire screen**. Capturing only the game window does not include separate overlay windows. The recording setting applies to both the panel and highlights. This does not inject anything into the game.

## Updates and local data

Background checks start about five seconds after launch and repeat every two minutes. An available release appears as a compact **Update / Skip** row in the overlay. Downloads start only when Update is clicked. Packages are SHA-256 checked; the helper replaces the application and restarts it, with startup-failure rollback. Settings and history stay in the existing per-user folder.

Data is stored under `%LOCALAPPDATA%/Vorax Lab`; the legacy folder name preserves existing profiles. Game-log discovery uses the running game and supported installation locations. Finding a log file alone does not prove that the game is currently writing useful events. Gameplay screenshots, logs, history and calculations remain local.

The portable ZIP and update manifest remain release assets for compatibility with installed automatic updaters. Most users should download the **Setup.exe**.

This is a distribution repository containing documentation and release downloads. Development sources, private recordings and user data are not published here. Release descriptions are in English.

## Credits

Vorax builds on the MIT-licensed [Moebing simulator](https://github.com/Moebing/Torchlight-Infinite-SS11-Vorax-simulator). Tartarus uses pinned resources from the original [Tartarus simulator](https://github.com/blahdot3h/tartarus-simulator). [TLI Overlay Plus](https://github.com/Giboork/tli-overlay-plus) informed interoperability research; its proprietary application is not redistributed.

Riftline is independent and is not affiliated with or endorsed by the game's developers or publishers. Game-derived names and artwork retain their respective rights.
