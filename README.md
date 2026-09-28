# CodeX5e Handoff

This public repository is a coordination bridge for the private CodeX5e project. It may contain sanitized specifications, task instructions, completion reports, and review notes.

Do not add application source code, credentials, private reference content, character data, or proprietary material.

The private `ironcheftomie/Codex5e` repository remains separate.

## Roadmap and data ownership

See [ROADMAP.md](ROADMAP.md) for the gated player releases through DM tools. Player characters and homebrew belong to the player: the Android app stores them locally on the player's phone, supports core use offline, and provides portable backup/export, import, and deletion. Future sync is opt-in; sharing with a DM is a deliberate player action. Verify actual installed-app storage and recovery behavior before claiming this release gate is met.

## Current task for local Codex — 2026-09-28

The owner has given final manual approval for CodeX5e v0.12. The public GitHub copy of the private app was still at v0.11 at the last cloud check. The authoritative v0.12 working copy is on the Chromebook. Do not derive v0.12 by modifying the old cloud checkout.

In the Chromebook's local `Codex5e` project:

1. Inspect `git status`, branch, remotes, recent commits, and the complete pending diff. Confirm this is the approved v0.12 checkout, including the dagger duplicate-key correction and regression coverage. If those are absent or the state is ambiguous, stop and report before changing Git history.
2. Run the project's complete validation: TypeScript, lint, all tests (including responsive/browser checks), production build, and `git diff --check`. Report exact counts and any warnings or unhandled errors. Do not call a run clean if workers report unhandled errors. Check local character persistence, export/import, backup/restore, and migrations with the scope available in v0.12; flag any gap against the device-ownership rule in the roadmap.
3. If the approved v0.12 code is present and every required gate passes, preserve it with a commit and v0.12 tag using the repository's existing release convention, then push the commit and tag to the **private** `ironcheftomie/Codex5e` repository. Never put app source in this public handoff repo. If the newly specified ownership gate reveals a material gap, report it for owner review before calling the milestone complete.
4. Report the commit SHA, tag, remote push result, and validation results. Do not deploy or begin v0.13 in this task.

After the private GitHub repo is current, use the Codex cloud environment for future reviewable tasks. v0.13 Homebrew Authoring is [queued separately](tasks/V013_HOMEBREW_AUTHORING.md), but it is outside this synchronization task.
