# Active task: v0.12 storage safety repair

**Status: ACTIVE — replaces the prior release-sync instruction.** Work in the authoritative local Chromebook `Codex5e` checkout on `v0.12-manual-test`. The private GitHub checkout was at v0.11 at last check. Do not start v0.13. Do not create a release commit or tag, push, merge, or deploy in this task.

## Why this task exists

The local ownership audit reported:
- Character and snapshot records in browser `localStorage`; imported content in IndexedDB.
- Deleted characters may return from historical migration keys.
- A storage read failure or unsupported stored version may be interpreted as an empty collection; a later save can overwrite prior data.
- Browser validation could not start in the current execution sandbox: Chromium socket/loopback operations returned `Operation not permitted`; zero checks completed. Do not treat this as a test pass.
- A full backup includes installed content definitions. A single-character export intentionally contains less; document this difference clearly.
- Android phone storage cannot be claimed as verified before an APK exists. See [ROADMAP.md](../ROADMAP.md).

The detailed local report is `V012_RELEASE_OWNERSHIP_AUDIT.md` in the Chromebook checkout. Read it and the current code before editing. The report mentions temporary reproducers; turn confirmed problems into durable regression tests.

## Implementation

1. Preserve the complete approved v0.12 working tree. Inspect status and diff before changing it. Do not reset, replace, or discard pending work.
2. Repair deletion and migration so a deleted character cannot reappear through any supported legacy key or migration path, including after restart and import/restore. Preserve other legitimate records.
3. Repair storage read/error handling so corruption, denied access, quota issues, or an unsupported future schema cannot silently become an empty state and then overwrite prior data. Fail safely with a recoverable error and keep the original bytes until a validated recovery action. Do not silently erase or downgrade.
4. Add focused regression tests for both bugs, migration/version edge cases, and backup/restore and deletion interactions. Use the repository's single source of truth and delete obsolete code.
5. Audit the single-character export versus full-backup distinction. Ensure the user-facing labels/instructions make it clear which option moves homebrew and installed packs. Flag any unresolved portability gap in the report.
6. Re-run TypeScript, ESLint, full unit suite, production build, `git diff --check`, and applicable responsive/browser checks. Report exact counts and all warnings/unhandled errors. If Chromium still cannot bind sockets because of the sandbox, record it as **blocked, zero browser checks**, and specify a safe execution environment or manual procedure for later verification. Do not claim browser tests passed.
7. Report changed files, the two original bug reproducers and their passing regression tests, remaining data risks, manual QA steps, and precise release blockers. Keep the changes in the local working tree for review. No release commit/tag/push/deployment or v0.13 work.

## Gate after this task

Owner reviews the fix report. Browser/responsive checks must run in a permitted environment and storage flows need manual QA. Then a separate instruction can authorize the v0.12 commit/tag/private push. The Android APK storage verification remains a later milestone; do not hold a web-only code snapshot to a nonexistent device test, but never claim phone ownership is already verified.
