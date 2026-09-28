# Queued task: v0.13 — Homebrew Authoring

**Status: QUEUED. Do not execute from this file until v0.12 is validated, committed, tagged, pushed to the private repository, and confirmed as the current cloud base.** The owner has manually approved v0.12, but synchronization must be verified first.

Read [ROADMAP.md](../ROADMAP.md), especially the device-local ownership rule. This task does not authorize v0.14 or DM tools.

## Goal

Let a player author and manage homebrew content within CodeX5e while preserving the app's single source of truth and the existing 2014 SRD baseline. Homebrew and character data belong to the player, remain usable offline, and are stored locally on the player's device in the installed app.

## Work order

1. Read the current private repository, its applicable instructions, tests, and v0.12 release state. Inventory current imported-content, persistence, and character-ownership models before proposing schema or UI changes.
2. Produce a concrete v0.13 implementation plan from the current code. Identify supported content types, editing and validation rules, stable IDs, ownership, local storage, character references, data migrations, portable backup/export/import, conflict handling, and recovery. Flag choices that need the owner's product decision.
3. Implement in reviewable slices only after the plan is grounded in the current code. Reuse canonical models; delete replaced code. Preserve characters and imported content across migrations. Do not silently upload content or require an account.
4. Validate TypeScript, lint, meaningful tests, production build, and browser/responsive behavior. Manually verify offline authoring, restart, character references, export/import on another device, and recovery without data loss.

## Release gate

Do not mark v0.13 approved, tag, merge, deploy, or begin v0.14 without explicit owner approval after manual QA. Keep all application source and private data in `ironcheftomie/Codex5e`; publish only sanitized instructions and reports here.
