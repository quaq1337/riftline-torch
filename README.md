<p align="center"><img src="assets/riftline-icon.png" width="88" alt="Riftline emblem"></p>
<h1 align="center">Riftline</h1>
<p align="center">A local, read-only companion for Torchlight: Infinite.</p>
<p align="center"><a href="https://github.com/quaq1337/riftline-torch/releases/latest">Download for Windows</a> · <a href="CHANGELOG.md">Changelog</a> · <a href="docs/GETTING_STARTED.md">Getting started</a> · <a href="https://github.com/quaq1337/riftline-torch/issues">Report an issue</a></p>

![Riftline key art](assets/riftline-keyart.png)

Riftline reads the English game screen and local game log, calculates Vorax choices on your computer, and highlights the recommended card and targets over the game. You make every game action yourself.

**Release 1 is v0.1.0.** Earlier 0.1–0.4 prototype numbers were private development builds; public versioning starts here. Future public releases use Semantic Versioning: patch fixes begin at 0.1.1. Every release includes English change notes.

## Features

- **Vorax advice:** card and target search, score forecasts, special potion chains, supported starting equipment, Intern Shelley tier profiles, and reroll evaluation using the observed remaining budget.
- **Automatic reading:** game-screen recognition assisted by log events. Manual board entry is a recovery option; unknown or inconsistent readings are surfaced.
- **Visible highlights:** cyan card and reroll outlines, green targets, and recommendations that remain through target selection.
- **Desktop integration:** tray startup, a compact overlay outside preparation, background capture pause, F8 refresh, and F9 pause.
- **History:** confirmed Vorax final scores and log-derived Tartarus Chromatic counts, separate from forecasts and incomplete observations.
- **Updates:** background checks and a compact Update / Skip row inside the overlay, SHA-256 verification, automatic restart and startup-failure rollback.
- **English and Russian UI:** Windows-region default and a manual language setting. Recognition currently requires English game text.

| Mechanic | Available | In development |
| --- | --- | --- |
| Vorax | OCR, log tracking, recommendations, highlights, history | Recognition coverage and end-to-end latency improvements |
| Tartarus (preview) | Board recognition, local route/consume/instrument/treasure guidance, highlights, logs and history | Complete effects, full-run reward optimization and wider live validation |

**Tartarus is a preview, not a full-run optimal-play advisor.** Approximate local guidance is marked `~`. Strict chain forecasts remain gated by verified effects. Unknown or unsupported states may have no highlight. Forecasts estimate outcomes using the implemented simulator; maximum scores and complete coverage of future game patches cannot be guaranteed.

## Install and play

1. Download `Riftline-<version>-Setup.exe` from [Releases](https://github.com/quaq1337/riftline-torch/releases).
2. Run the installer. It installs the full application for your Windows account and creates a desktop shortcut. No manual extraction is needed.
3. Launch Riftline. The dashboard starts in the tray and the overlay appears. Open the board from the tray or overlay.
4. Run Torchlight: Infinite in English, preferably borderless windowed. Enter Vorax Surgical Preparation; reading starts automatically.
5. For Tartarus, fresh log events select the module automatically. If game logs are disabled or stale, open the dashboard → Tartarus → **Enable Tartarus reading**, then press F8. Choose **Return to Vorax** when needed.
6. Set your Intern Shelley tier on the main board if applicable. Check the log indicator, then make the highlighted choices yourself.

No separate Python or Node.js installation is needed. Windows x64 is supported. The installer needs no administrator privileges and uses `%LOCALAPPDATA%/Programs/Riftline` by default. All OCR models and calculation files are included unchanged, with lossless compression. The portable ZIP remains available for portable use and existing automatic updaters.

| Control | Action |
| --- | --- |
| F8 / Refresh | Capture and read the current game screen |
| Picture | Capture the game directly into recognition |
| F9 | Pause or resume automatic reading |
| Close dashboard | Keep Riftline running in the tray |
| Tray → Exit | Fully close Riftline |

Capture follows the game window and DPI. Resampled real captures were checked at 720p, 900p, 1080p, 1440p and 4K in 16:9; this does not replace live testing on each device. Other aspect ratios, unusual UI scales and overlays covering controls may require correction.

## Data, logs and updates

Writable folders are created automatically under `%LOCALAPPDATA%/Vorax Lab`. The legacy folder name preserves settings and history from private builds. All portable releases use the same per-user folder.

```text
Vorax Lab/
  settings.json       Language, pet, overlay and mechanic preferences
  runs.sqlite3        Local run history
  records/vorax/      Confirmed recorded Vorax choices
  records/tartarus/   Distinct recognized Tartarus decisions and diagnostics
  updates/            Downloads and update status
```

`UE_game.log` is discovered from the running game, configured Steam libraries and supported installation locations. No developer-specific path is bundled. The manual picker is a fallback; log reading is enabled by default and can be disabled explicitly.

Background release checks begin about five seconds after startup and repeat every two minutes, with a one-minute retry after network errors. They read a small latest-version manifest; no application download starts until **Update** is clicked. A discovered release stays in the compact overlay. **Update** verifies the archive, closes the app, replaces its folder and restarts. **Skip** hides that version; newer releases can notify again. A manual check in Settings can show a skipped release. If startup fails, the helper restores the previous application. [Update design and recovery](docs/UPDATES.md).

Screenshots, logs, history and calculations remain local. The updater contacts GitHub for release metadata and downloads, without uploading gameplay data. [Privacy and storage](docs/PRIVACY.md).

## Development

Use Windows x64, Python 3.12 and Node.js 24. From the repository root:

```powershell
python -m pip install -r requirements.txt
python app.py --demo
python -m unittest discover -s tests -p "test_*.py"
node --test --test-isolation=none tests/*.test.mjs
python build.py
python tools/package_release.py
python tools/build_installer.py
```

Private capture tests skip when their fixtures are absent. Public tests cover rules, state tracking, update validation and rollback. See [Development](docs/DEVELOPMENT.md), [Training](docs/TRAINING.md), [Roadmap](docs/ROADMAP.md) and [Contributing](CONTRIBUTING.md).

## Credits and license

The Vorax simulator builds on the MIT-licensed [Moebing simulator](https://github.com/Moebing/Torchlight-Infinite-SS11-Vorax-simulator). Public simulators and [TLI Overlay Plus](https://github.com/Giboork/tli-overlay-plus) informed interoperability research; their proprietary applications are not redistributed.

Project-authored code uses the [MIT License](LICENSE). Third-party software and game-derived names, portraits and recognition crops retain their respective rights; see [Third-party notices](THIRD_PARTY_NOTICES.md). Riftline is independent and is not affiliated with or endorsed by the game's developers or publishers.
