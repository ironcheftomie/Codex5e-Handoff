# CodeX5e Handoff

This public repository is a coordination bridge for the private CodeX5e project. It may contain sanitized specifications, task instructions, completion reports, and review notes.

Do not add application source code, credentials, private reference content, character data, or proprietary material.

The private `ironcheftomie/Codex5e` repository remains separate.

## Roadmap and data ownership

See [ROADMAP.md](ROADMAP.md) for the gated player releases through DM tools. Player characters and homebrew belong to the player: the future Android app stores them locally on the player's phone, supports core use offline, and provides portable backup/export, import, and deletion. Future sync is opt-in; sharing with a DM is a deliberate player action. Verify actual installed-app storage and recovery behavior once an APK exists.

## Current task for local Codex — 2026-09-28

**Repair v0.12 storage safety before release:** follow [tasks/V012_STORAGE_SAFETY.md](tasks/V012_STORAGE_SAFETY.md) in the authoritative Chromebook checkout. The latest audit found resurrection of deleted characters from legacy keys and possible overwrite after failed/unsupported storage reads. Browser validation was blocked by sandbox socket permissions, with zero checks completed.

The owner previously approved v0.12 manual QA, but this new audit uncovered release blockers. Preserve the working tree; fix and test the issues; report the findings. **Do not commit, tag, push, deploy, or start v0.13 from this task.** A later release-sync instruction will follow review and validation.

[v0.13 Homebrew Authoring](tasks/V013_HOMEBREW_AUTHORING.md) remains queued and must not be executed until v0.12 is safely synchronized to the private repository.
