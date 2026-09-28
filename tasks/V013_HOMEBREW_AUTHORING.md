# Queued task: v0.13 — Homebrew Authoring

**Status: QUEUED. Do not execute from this file until v0.12 is validated, committed, tagged, pushed to the private repository, and confirmed as the current cloud base.** The owner has manually approved v0.12, but synchronization must be verified first.

## Goal

Let a player author and manage homebrew content within CodeX5e while preserving the app's single source of truth and the existing 2014 SRD baseline. This milestone follows the approved v0.12 creation and ownership work.

## Work order

1. Read the current private repository, its applicable instructions, tests, and v0.12 release state. Inventory current imported-content and character-ownership models before proposing schema or UI changes.
2. Produce a concrete v0.13 implementation plan from the current code. Identify content types, editing and validation rules, persistence, import/export behavior, references from characters, migration/recovery behavior, and legal/content boundaries. Flag choices that need the owner's product decision.
3. Implement in reviewable slices only after the plan is grounded in the current code. Reuse canonical models; delete replaced code. Preserve characters and imported content across migrations.
4. Validate TypeScript, lint, meaningful tests, production build, and browser/responsive behavior. Report exact results and remaining manual QA.

## Release gate

Do not mark v0.13 approved, tag, merge, deploy, or begin v0.14 without explicit owner approval after manual QA. Keep all application source and private data in `ironcheftomie/Codex5e`; publish only sanitized instructions and reports here.
