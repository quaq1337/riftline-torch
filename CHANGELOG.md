# Changelog

Public release notes are written in English. Public versioning starts at 0.1.0; private prototype versions are not part of this sequence.

## [Unreleased]

### Planned
- Complete and validate Tartarus board recognition and decision support.
- Improve live end-to-end Vorax latency and recognition coverage.

## [0.3.4] - 2026-10-27

### Tartarus input and first-offer recovery
- Do not treat clicks on Riftline's non-activating overlay controls as Tartarus gameplay. Read the window under the pointer; preserve game clicks through the transparent highlight layer.
- Retain pointer target and normalized click position in Tartarus input diagnostics.
- Recover the unchanged, uncommitted reopened first offer after unclassified clicks or a background gap only when the original live witness, exact old and current log lifecycle, three current unselected cards, gray Confirm, zero objective progress and unchanged zero refresh counter all agree.
- Preserve the earlier unresolved input history separately with checkpoint provenance. Never erase a committed tool, a typed Select/Confirm, a played-board checkpoint, unknown effects, changed cards or a changed resource counter to obtain a recommendation.
- Leave the released Vorax engine, recognition and input behavior unchanged.

Tartarus remains a preview. Verification includes the actual saved failing frame and its recorded unclassified clicks/focus gaps, not a complete live-run acceptance or a guaranteed Rainbow result.

## [0.3.3] - 2026-10-27

### Reopened first instrument selection
- Recognize the game's shipping-log `Page@ OpenView` lifecycle when detailed UI recording is disabled. A reopened board and tool popup are distinct from a newly observed Start button.
- Reconnect an unchanged, uncommitted first tool selection after restarting the game, using the application's original live input witness, the rotated game's exact initial/teardown history, the current Main-to-Relic reopening, matching three card identities, a positively read zero-progress objective and the unchanged refresh counter.
- Keep the recovered start proof separate from current log facts. Do not turn recovered logs into a newly observed start or use wall-clock drift to correlate old mouse input.
- Preserve the confirmed initial tool through its typed selection/Confirm and current shipping-log closure. Unknown buffs, gameplay gaps and contradictory cards remain blocked.
- Include the actual lifecycle evidence in unavailable-choice diagnostics and remove stale failure text after a successful calculation.

Tartarus remains a preview. This recovery is limited to the uncommitted first offer with a retained original live witness; it does not reconstruct an arbitrary partially played run or guarantee a Rainbow result.

## [0.3.2] - 2026-10-27

### Tartarus entry, Guillotine sensitivity and pet resources
- Treat a mouse input in the positively logged initial Task popup as modal input even when the player confirms before the first OCR frame. It no longer becomes an unknown gameplay action that permanently blocks the initial instrument evaluation.
- Preserve the input journal in early gap diagnostics, including the exact blocking input. Unknown gameplay, unreviewed starting effects and later-run gaps remain fenced.
- Restore an uncommitted first offer after restarting only when its saved live input witness, exact UI timeline, cards, current resources and same-boot clock correlation agree. Recovered logs alone cannot restore an arbitrary played board.
- Keep Fanged Guillotine in current and future choices. Evaluate its unresolved Oppress behavior under 24 explicit sensitivity hypotheses, including upgrade probability, trigger scope, bonus gating and Code changes on failure. Choose the action with the strongest minimum tested-scenario mean and show the scenario range. These are model estimates, not measured game probabilities, exhaustive bounds or guaranteed results.
- Reuse completed trials only when no potentially affected Guillotine bite occurred. This preserves the existing rollout budget while avoiding repeated work across unaffected scenarios.
- Accept a positively observed consumed meal with zero Wolf growth under the explicit Oppress capability. Keep unrelated cell changes, missing effects and invalid action histories blocked.
- Add an independent Twin Inquisitors tier selector to the Tartarus dashboard. Respect the actual current refresh counter, preserve the shared pool through subsequent tool offers and treasures, debit each refresh once and never invent repeated future pet grants.
- Record literal UI event timestamps and retain the original recording identity as provenance during narrowly verified first-offer recovery. Vorax logic and its frozen isolation baseline remain unchanged.

Tartarus remains a preview. The saved original first-offer failure is covered with the production 8-world × 8-seed budget and one primary highlight. A complete live run has not passed acceptance; complex unread states still require positive evidence. Oppress scenario ranges do not guarantee a Rainbow total. User settings and history are retained.

## [0.3.1] - 2026-10-26

### Mechanic switching and Rainbow display hotfix
- Check the active mechanic independently of the shared strategy queue every 250 ms while the game is foreground. Keep checking after a recognized Tartarus frame, so returning to Vorax no longer waits for the Tartarus reader to fail.
- Reuse high-confidence heading templates before requesting OCR. Cache unchanged positive heading pixels, throttle OCR fallback and skip it while the shared reader is occupied instead of queuing behind it.
- Switch the overlay's module header immediately after positive recognition and invalidate advice from the previous mechanic.
- Show collected Chromatic prisoners in a compact label, with the estimated final total in the main metric. Add the same forecast to the Tartarus dashboard. Reject forecasts for another choice or an older confirmed containment count; display a dash when no valid estimate is available.

This is a prerelease and includes the Tartarus integration described below. Remaining limitations still apply; these changes do not establish complete live-run acceptance or guarantee a particular Rainbow total.

## [0.3.0] - 2026-10-26

### Tartarus integration preview
- Replace local move ranking with the pinned simulator's remaining-run evaluation for confirmed supported states. Show one primary action and an estimated final total of Chromatic prisoners.
- Retain all confirmed instruments, objectives, starting buffs and consecutive reward queues. Reconcile supported Consume and Bestow rewards with the current board, including Opulence and later instrument choices.
- Preserve card selection and confirmation through refreshed frames. Deduplicate input transactions and distinguish treasure inspection from actual acquisition.
- Read the current board behind Warden's Treasure and return through positively identified view controls. Read-only navigation is bounded; it never chooses an instrument or confirms a gameplay action.
- Separate Tartarus jobs from Vorax work and avoid redundant route recognition while Tartarus is positively recognized.
- Obtain the five exact, hash-verified simulator resources directly from the original pinned repository when first needed, then retain them in per-user storage. The application payload does not redistribute the research checkout. An internet connection is required for the first component download.
- Keep the released Vorax 0.2.3 implementation unchanged.

This is a prerelease for integration testing, not a complete Tartarus advisor. A whole live run has not passed acceptance. Unknown effects and incomplete observations block advice rather than inventing a state. Fanged Guillotine/Oppress, some marked/timed states and complex Horn/Cage/Revenge transitions remain unsupported. Read-only navigation has not been verified against the live game's posted-input handling. Do not use this preview as the sole basis for a valuable run.

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
