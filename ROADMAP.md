# CodeX5e roadmap — player app through DM tools

Planning roadmap as of 2026-09-28. Milestones are sequential release gates, not permission to begin later work. Application source and real character data stay in the private repository or on the player's device, never in this public handoff.

## Product rule: player-owned, device-local character data

- The installed Android app stores character sheets, inventory, spells, notes, homebrew, and campaign participation data on the player's phone. The app's core character workflows work offline without account creation or a server.
- A player can export a complete, portable backup, import it onto another device, and delete their local copy. Imports validate data before replacing or merging anything and do not silently overwrite existing characters.
- App updates and data migrations preserve characters and homebrew. Test restart, app update, backup/restore, and failure recovery before release. Explain any platform storage limitation plainly in the product.
- Sync or cloud backup, if added later, is opt-in with clear destination, controls, and deletion. Sharing a character with a DM is a deliberate player action. DM tools do not take ownership of the player's master copy.
- Do not claim that a browser tab's storage guarantees permanent phone ownership. Verify the installed-app storage implementation and backup/restore on real devices.

## Player releases

### v0.12 — Advanced creation and ownership (manual approval granted; private GitHub sync pending)
- Create legal level 1–20 characters directly, including multiclass and higher-level choices; preserve a single canonical character model.
- Duplicate characters, export/import them, and recover from backups; migrate existing saved data without loss.
- Finish the duplicate-dagger inventory ID correction and regression tests in the authoritative Chromebook copy. Validate creation, inventory, save/load, export/import, backup/restore, TypeScript, lint, tests, browser/responsive checks, and build.
- Exit: verify the local approved state, commit/tag/push v0.12 to **private** GitHub, then confirm cloud tasks see that revision. Do not start v0.13 from the older v0.11 cloud checkout.

### v0.13 — Homebrew Authoring (queued)
- Define supported content types from the current code and product decision, then provide forms to create, edit, validate, use, export, and import each type.
- Give homebrew stable IDs and ownership. Preserve character references when content changes or is removed; handle conflicts and bad imports without data loss.
- Keep authored content on device with the player's characters, available offline and included in portable backups.
- Exit: automated checks plus manual creation, edit, character-reference, restart, migration, export/import, and recovery QA; explicit owner approval before release.

### v0.14 — Player experience and polish (future)
- Make creation, sheet, inventory, spells, combat, and dice readable and fast on phones and desktop.
- Improve navigation, feedback, accessibility, keyboard/touch use, responsive layouts, 3D dice, reduced motion, and a simpler dice fallback.
- Exit: realistic end-to-end sessions on small and large screens; prove effects never block core actions and device-local data still persists.

### v0.14.1 — First Android APK (future)
- Package the player app and test install, launch, offline use, local storage, backup/restore, closing/reopening, and upgrading on real Android devices.
- Confirm character data is stored in app-controlled local storage on the player's phone and remains recoverable if the app/device is lost through user-made exports. Document the consequences of uninstalling or clearing app data.
- Exit: a tester installs, creates/uses a character offline, reopens, upgrades, exports, imports, and recovers without losing data.

### v0.15 — Hardening and feature freeze (future)
- Fix important beta blockers: data integrity, migrations, offline recovery, accessibility, security, performance, errors, and release consistency.
- Freeze new player features while validating complete character and homebrew preservation.
- Exit: no known critical loss-of-data or blocked-play defects; repeatable clean release build and manual gate.

### v0.16 — Player beta (future)
- Test with a small external group across devices and real sessions. Gather reports on usability, failures, and data portability.
- Ship focused fixes and verify every update preserves existing local data and backup compatibility.
- Exit: core journey works reliably for beta players, including offline use and recovery.

### v1.0 — Player release (future)
- Publish the stable player app with accurate features, supported devices, backup/restore instructions, and issue reporting.
- Exit: release build matches tested behavior; character ownership, portability, and recoverability remain explicit promises.

## DM tools phase (future, gated after player foundation)

1. **Campaign and party:** multiple campaigns, party rosters, NPCs, notes, sessions, and persistent state. Players choose what character details to share; DM copies/links are scoped to the campaign.
2. **Quick generators:** edit-and-save NPC, encounter, loot, and establishment results. Reduce preparation time without taking away DM control.
3. **Places and dungeons:** shops and inns; procedurally varied Small, Medium, Large, and Sprawling dungeons with coherent routes, rooms, traps, puzzles, secrets, hazards, and alternate paths. Combat rooms give adequate tactical space; boss rooms are larger still. Repeated generation varies layout and contents.
4. **Encounter control:** structured party-aware difficulty including an explicitly extreme **Kill Party** option, fully reviewable and editable before play; initiative, enemy state, rewards, and outcomes.
5. **Maps and tactical play:** fog of war, exploration reveals, positioning, larger battles, digital maps, and optional STL miniature outputs where practical.
6. **Persistent world and awards:** linked campaign consequences, inventories, and history; selected XP recipients and rewards take effect only with DM approval.
7. **DM assistance:** first human-run tools, then inspectable AI suggestions, then an optional ChatGPT-as-DM mode. Material changes to characters and campaign state must be visible, reversible where feasible, and within the sharing permissions set by players and DM.

Implement and manually verify one DM layer at a time. Preserve the player's device-local master character data throughout.
