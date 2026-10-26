# Changelog

Public release notes are written in English. Public versioning starts at 0.1.0; private prototype versions are not part of this sequence.

## [Unreleased]

### Planned
- Complete and validate Tartarus board recognition and decision support.
- Improve live end-to-end Vorax latency and recognition coverage.

## [0.2.3] - 2026-10-26

### Vorax forecast correction
- Preserve claimed 8,000/28,000 reward flags when reconstructing protocol-round state. Forecasts for rounds 11–13 no longer receive advanced instruments that were already earned earlier in the run.
- Restore remaining refresh counts before taking the protocol path, just as for potion and instrument choices.
- Add regression coverage for protocol reconstruction, unchanged held instruments and final-score simulation without duplicate rewards.
- Save protocol forecasts and their current score in latency diagnostics so reported forecast differences can be audited.

This fixes a reproduced forecast inflation bug, not all model uncertainty. Tartarus's full-run rewrite remains under development and is not included.

## [0.2.2] - 2026-10-26

### Vorax recognition hotfix
- Recover the shifted five-card fan after Potion Kit (Large) using three independently recognized title anchors.
- Read each recovered card slot separately so adjacent Pure Leech Solution and Hollow Spinal Solution titles cannot merge or fill the same slot twice.
- Keep round, total activity, card-name confidence and complete-offer validation intact. No guessed card or missing effect is accepted to bypass a recognition failure.
- Validate the reported round-five frame with all five cards recognized and no manual corrections.
- Prefer the running game's own log over a newer log from another installation.

Tartarus remains an experimental preview. The ongoing full-run strategy and effect-integration rewrite is not included in this Vorax-only hotfix.

## [0.2.1] - 2026-10-26

### Live Tartarus fixes
- Identify Vorax and Tartarus from positive current-screen headings and switch their capture/advice pipelines automatically, independently of game-log freshness or the last manually opened dashboard page. Preserve individual mechanic enablement and pause controls.
- Recognize Long-Chained Shackles from its complete English name. The observed initial offer with Shackles, Searing Branding Iron and Barbed Whip no longer loses all guidance because one catalog entry was missing.
- Record the Shackles' verified movement condition and keep it separate from consume modifiers. Retain explicit local-policy tradeoffs rather than claiming full-run optimality.
- Reject a delayed routing result after a newer log transition. Start a fresh Vorax entry context when screen detection switches back from Tartarus.

## [0.2.0] - 2026-10-26

### Tartarus preview
- Connect the Tartarus reader and session advisor to automatic game-window capture and the overlay. Fresh Tartarus log events select the mechanic; a dashboard button provides a fallback when logs are unavailable.
- Highlight observed routes, consume targets, instrument and treasure choices, plus the current-board preview workflow. Approximate local guidance is explicitly marked `~`; this release does not claim complete effects or full-run optimality.
- Reject superseded results after clicks, run changes and background transitions. Scale validated normalized highlights to the game client rectangle, including secondary monitors. F8 reads immediately and F9 pauses.
- Reuse the existing local OCR instance and serialize recognition. Preserve the verified same-frame OCR improvements; do not introduce another recorder or browser capture process. Pause recognition when the game is not foreground.
- Keep confirmed rainbow history separate from forecasts. Create Tartarus recording folders automatically and save distinct recognized decisions plus the latest game frame for diagnostics.
- Bundle the three numeric recognition assets and independent current-chain planner. Unsupported effects stay explicit; no fixed priority is assigned to incident exclamation marks.
- Enable the newly available Tartarus preview profile once when migrating old unavailable defaults; preserve subsequent user opt-outs, settings and history.

Known limits: English game UI, incomplete recognition of instruments/marks/incidents, approximate patrol/tool/treasure policy, and no automatic End action. New event-transition and reward-analysis modules are included for development but are not presented as a complete live reward simulator. This is the first live-play preview and still requires real-run validation.

## [0.1.8] - 2026-10-26

### Automatic update discovery
- Check for updates about 5 seconds after startup and every 2 minutes instead of every 6 hours. Retry temporary network failures after 1 minute, without requiring a manual check.
- Use the small latest-release manifest for recurring background checks, avoiding the shared anonymous REST quota. Request revalidation of latest metadata rather than relying on a stale cached response. Manual checks retain the release-feed path and its fallback.
- Keep an already discovered update in the compact overlay. Background polling does not expand the advice body, take focus, download the application or install it.
- Respect Skip even if an earlier request finishes afterward. Ignore late metadata replies during a chosen download so its version and progress cannot be replaced.
- Cancel the polling timer on exit. Regression tests simulate new releases, offline recovery and timer-driven discovery without user actions or network access.

The new polling schedule applies after installing this version. Older clients still need their existing manual check once to obtain it. Installation remains an explicit Update action. Vorax calculation quality and the v0.1.7 performance improvements are retained.

## [0.1.7] - 2026-10-26

### Vorax computation performance
- Use a faster state-copy path in rollout branches while preserving the engine prototype, every own rule field and isolation of mutable state.
- Reuse the immutable event-driven instrument set at round settlement instead of rebuilding it repeatedly. Event journals and cascade order remain intact.
- Preserve game rules, model weights, complete action/target enumeration, reroll confidence checks, sample limits and search budgets.

### Validation
- Five alternating batches of 1,000 seeded episodes each produce exactly the same scores as v0.1.6; serial computation is about 30% faster in this local benchmark.
- On three saved boards, a four-worker comparison with the bundled weights and exactly 256 samples per action produces identical full results. Median search times across three paired trials changed from 880 to 421 ms, 93 to 38 ms, and 388 to 171 ms.
- These are offline search measurements, excluding capture, OCR and physical monitor presentation. Live end-to-end improvement still needs confirmation on new card decisions.
- OCR thread-count and parallel-retry experiments did not improve the paired measurements and were not included. Recognition and display behavior remain unchanged.

## [0.1.6] - 2026-10-26

### Compact update notification
- Replace the separate update window and release-notes panel with one small row inside the existing overlay: version, Update and Skip.
- Keep the row accessible while the overlay is compact, without expanding the advice body or taking keyboard focus.
- Show download percentage, verification and download failures in that same row. Progress does not move or resize the overlay; controls remain in place and are disabled during installation.
- Preserve the verified download, restart, rollback and per-version Skip behavior. No download or installation begins until Update is clicked.

### Validation and compatibility
- Added native UI checks for no additional notification windows, compact RU/EN layout, stable progress geometry, skip persistence and inline retry after failure.
- Existing v0.1.5 and earlier installations still use their original notification once when updating to this version. Later notifications use the inline row.
- Recognition models, game rules, calculation quality and local user data are unchanged.

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
