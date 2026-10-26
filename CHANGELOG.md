# Changelog

Public release notes are written in English. Public versioning starts at 0.1.0; private prototype versions are not part of this sequence.

## [Unreleased]

### Planned
- Complete and validate Tartarus board recognition and decision support.
- Improve live end-to-end Vorax latency and recognition coverage.

## [0.1.5] - 2026-10-26

### Automatic reading and startup
- Check for a Vorax heading, recognizable offer or final protocol counter before validating a board. World and menu frames no longer become missing-round/manual-entry warnings after repeated automatic scans.
- Keep the overlay compact outside a confirmed preparation scene and resume screen recognition even when a readable historical log has no fresh events.
- Accept confidently positioned split round-counter tokens and common OCR one-glyph variants. Retry failed counters in tighter and wider crops automatically; missing or conflicting numbers remain unknown rather than inheriting a saved round.

### Log status
- Distinguish finding an old log, observing new file writes, receiving mechanic events and losing fresh activity. Reading an existing file alone no longer displays "Log considered".
- Do not use an unconfirmed historical lifecycle to open the overlay or disable screen fallback. Automatic log reading remains enabled; the application does not claim to enable logging inside the game client.
- Include round-crop evidence and live-log connection state in local diagnostics.

### Validation and distribution
- Added startup-scene, historical-log, rotation, counter-splitting and ambiguity regression coverage.
- Six previously readable saved Vorax frames retain identical boards; resampled 16:9 capture checks pass from 720p through 4K. Live behavior on a friend's PC still needs confirmation.
- Offline EXE installer and compatible automatic-update assets are provided together. Models, calculation rules and search sample limits are unchanged.

## [0.1.4] - 2026-10-25

### Overlay responsiveness
- Request native repaint immediately after updating advice, and restore the overlay's topmost order without taking keyboard focus. Window movement no longer stands in for a presentation request.
- Ignore repeated open notifications for an already open preparation screen instead of cancelling and restarting the same read.
- Preserve the first confirmation/change timestamp across subsequent scene notifications. Keep a bounded per-decision latency journal, so a quick protocol forecast cannot overwrite the evidence of a slow card choice.

### Computation
- Reduce temporary allocations in action enumeration, policy features and ritual continuation evaluation. Action order, formulas, weights and sample limits are unchanged.
- Independent checks against v0.1.3 match 324 seeded episode outcomes and a complete fixed-sample search, including raw alternative scores.

### Distribution
- Development sources and their full history are now private. The unchanged public repository URL distributes README, changelog and releases only; all four existing release assets were migrated with identical digests.
- Public update checks continue to use the same URL. Future public release tags refer only to documentation commits.

### Measurement
- Native repaint timing still does not measure physical monitor presentation. Live card-choice latency must be assessed separately from protocol forecasts.

## [0.1.3] — 2026-10-25

### Performance
- Capture the game rectangle directly with a reusable native bitmap during stability checks, rather than copying the whole virtual desktop. Pillow remains the fallback.
- Read ordinary card titles before description text, with the previous wider reading area retained when any title is uncertain.
- Reduce unused padding for short OCR text while retaining full widths for long lines.
- Cancel obsolete reads and calculations when the game's offer changes, then schedule the new scene promptly.
- Drain bounded bursts of game-log data so recent Vorax and Tartarus events do not wait behind old combat messages.

### Diagnostics and validation
- Added per-scene attempt traces, capture backend, reader-lock wait, log delivery delay and game-event-to-advice timing. Tk publication timing is not a physical-display measurement.
- On six saved frames, old and new OCR produced identical boards and readiness. Five frames read faster in the paired check; mean read time changed from about 638 ms to 471 ms. This is an offline OCR comparison, not a live end-to-end latency guarantee.
- Resampled 720p–4K recognition checks pass. Native capture tests use synthetic pixels and cover resize, buffer reuse and fallback cleanup.
- The recommendation engine, sample counts, game rules and model weights are unchanged.

## [0.1.2] — 2026-10-25

### Added
- A Riftline desktop shortcut is created automatically on the first normal launch of a portable release.
- Windows Known Folders support redirected/OneDrive desktops and Unicode paths. The shortcut uses the executable's icon and the portable application's working directory.
- Repeated launches do not create duplicates. Moving the portable folder retargets an owned shortcut; unrelated shortcuts are preserved. A deliberately deleted shortcut is not recreated on every launch.

### Reliability
- Shortcut creation runs in the background and cannot block or fail application startup. Development, demo and smoke-test runs do not modify the real desktop.
- Auto-updates preserve the executable path, so the shortcut continues to work.

### Validation
- Native Shell Link tests cover Unicode paths, duplicate prevention, moved folders, unrelated files, manual deletion and nonfatal failures.
- The reference website's update notification was checked separately; no rule changes were inferred from its bundle update. See docs/REFERENCE_AUDIT.md.

## [0.1.1] — 2026-10-25

### Fixed
- Update checks fall back to the repository's direct latest-release manifest when GitHub's anonymous REST API is rate-limited or unavailable.
- The direct manifest carries English release notes and keeps the same product, platform, version, archive-size and SHA-256 validation.
- Skip and manual recheck behavior is preserved on the fallback path.

### Validation
- 103 Python checks and 50 Node checks pass locally; four private-capture cases skip in clean checkouts.
- The direct public release endpoint and frozen app startup were checked.

## [0.1.0] — 2026-10-25

### Added
- First public Riftline Windows x64 portable release.
- GitHub update checks with Update and Skip controls, SHA-256 verification, automatic installation and restart, and startup-failure rollback.
- A dashboard version label and manual update check in Settings.
- Automatic per-user records and update folders; settings, models and history stay separate from application files.
- English documentation, contribution guidelines, issue templates, CI and release packaging.

### Included from private development
- Vorax OCR and game-log tracking, card and target advice, reroll evaluation, supported starting equipment and special potion chains.
- English/Russian interface, Intern Shelley tier selector, tray startup and game overlay.
- Persistent high-contrast highlights and detected reroll-button geometry.
- Cached heading recognition, single-item OCR batches and equivalent planner feature calculations to reduce processing time.
- Vorax final-score history and Tartarus log-based Chromatic statistics.

### Validation
- 101 Python checks and 50 Node checks pass locally. Four private-capture tests skip in a clean public checkout; all remaining public checks pass.
- The frozen app starts with a clean profile. An isolated Windows update test replaces the portable directory, starts the actual frozen app and preserves a custom settings value and pet tier.
- Rollback tests cover failed new startup and a failed replacement-folder move.

### Known limitations
- English game text and 16:9 layouts provide the recognition baseline; other layouts require more testing.
- Tartarus recommendations are in development. Statistics work; the full advisor is gated.
- Recognition can fail on animations, covered controls and unverified effects. Forecasts are estimates, not guaranteed scores.
- Builds are not code-signed. Updates require GitHub access and a writable installation folder. The previous portable folder is retained for recovery.
- Private builds without an updater require the first public release to be extracted and launched once.

[Unreleased]: https://github.com/quaq1337/riftline-torch/compare/v0.1.4...HEAD
[0.1.0]: https://github.com/quaq1337/riftline-torch/releases/tag/v0.1.0

[0.1.1]: https://github.com/quaq1337/riftline-torch/releases/tag/v0.1.1

[0.1.2]: https://github.com/quaq1337/riftline-torch/releases/tag/v0.1.2

[0.1.3]: https://github.com/quaq1337/riftline-torch/releases/tag/v0.1.3

[0.1.4]: https://github.com/quaq1337/riftline-torch/releases/tag/v0.1.4
