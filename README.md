# Riftline

A local Windows companion for Torchlight: Infinite, with Vorax recommendations and game overlays.

**[Download the latest Windows installer](https://github.com/quaq1337/riftline-torch/releases/latest)** · [Release history](https://github.com/quaq1337/riftline-torch/releases) · [Changelog](CHANGELOG.md) · [Report a problem](https://github.com/quaq1337/riftline-torch/issues)

This public repository distributes the application and release notes. Development sources and their history are maintained separately in a private repository.

## Install

1. Download **`Riftline-<version>-Setup.exe`** from Releases.
2. Run it to install the full application and create a desktop shortcut. No manual extraction is needed.
3. Launch Riftline. The dashboard starts in the tray and the overlay appears.
4. Start Torchlight: Infinite in English, preferably borderless windowed, and enter Vorax Surgical Preparation.
5. Set your Intern Shelley tier on the main board if applicable, check the log indicator, and make the highlighted choices yourself.

No separate Python or Node.js installation is required. Windows x64 is supported. The offline installer needs no administrator rights and installs under `%LOCALAPPDATA%/Programs/Riftline` by default. It includes every original application file and OCR model, with lossless compression; recognition and calculation quality are unchanged. The app reads the screen and local game log; it does not click game controls.

## Features and current scope

- Vorax card/target recommendations, score forecasts, special potion chains, supported starting equipment and reroll-budget checks.
- Automatic screen reading assisted by game-log events, with direct refresh and manual correction for recognition failures.
- High-contrast card, target and reroll highlights; a compact overlay outside preparation.
- English/Russian interface, Windows-region default, pet tier selection and local run history.
- A compact update row inside the overlay with **Update / Skip**, inline download progress, verified files, restart and startup-failure rollback.
- Tartarus log-based archive statistics. The full Tartarus advisor is still in development.

Game-card recognition currently requires **English text**. Capture and highlight coordinates follow the game window. Resampled 16:9 captures from 720p through 4K were checked; unusual aspect ratios, UI scales and covered controls need additional validation. Forecasts are estimates and do not guarantee a maximum score.

## Controls

| Control | Action |
| --- | --- |
| F8 / Refresh | Capture and read the game |
| Picture | Send a fresh game capture directly into recognition |
| F9 | Pause/resume automatic reading |
| Close dashboard | Keep the app running in the tray |
| Tray → Exit | Fully close Riftline |

## Storage and updates

Writable folders are created under `%LOCALAPPDATA%/Vorax Lab`. The legacy name preserves settings, local models, recorded choices and run history across versions. Game-log discovery uses the running game and supported installation/Steam locations; a manual picker is available if discovery fails.

Choose **Update** when notified to download, verify, replace the portable files and restart. **Skip** hides that release; Settings has a manual update check. Settings and history stay in the per-user data folder. Keep the installation folder in place so the desktop shortcut remains valid. A previous app folder is retained for recovery.

Screenshots, logs and gameplay calculations stay local. GitHub receives release/download requests; gameplay data is not uploaded automatically. Review any diagnostics before attaching them to a public issue.

Each release includes English change notes and an offline **Setup.exe installer** with its SHA-256 checksum. The compatibility ZIP, `riftline-update.json` and `SHA256SUMS` are retained for portable use and existing automatic updaters; first-time users should choose Setup.exe. GitHub's automatically generated source-code archives contain only this distribution repository's documents.

## Support and notices

Include the Riftline version, Windows/game versions, English game language, resolution, scaling and reproduction steps in an issue. Redact account names, chat and personal paths.

Riftline is an independent project, unaffiliated with the game's developers or publishers. The distribution includes required notices and licenses, including the MIT-licensed Moebing Vorax simulator and other third-party components. Game names and artwork retain their respective owners' rights.
