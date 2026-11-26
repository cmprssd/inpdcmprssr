# inpdcmprssr

An in-place decompressor: extracts a compressed file and frees (hole-punches) the archive's
already-read bytes as it goes, so extracting needs room for the output only, not archive +
output. A Rust library crate (used by the cmprssd engines, nfsh first) plus a small CLI.

The spec is `docs/BRIEF.md`; decisions are in `docs/DECISIONS.md`.

## Overrides the cmprssd org rules

This is a library, not a game engine. Of `~/organizations/cmprssd/CLAUDE.md`, only the shared
tooling applies (Rust, `local-ci`, `docs/MAP.md`). **No progress page and no disc build.**
Reason in `docs/DECISIONS.md` (2026-11-11).

## Not doing

- No GUI or desktop app: a library and a CLI only.
- No compression: it only extracts. Building packages stays in the engines' own tooling.
- No RAR or 7z, now or later.
- No encrypted archives: password-protected ZIPs are refused.

## Constraints

- Development costs $0 (workspace rule).
- Licence: MIT or Apache-2.0.
- Of the cmprssd org rules, only the shared tooling applies (Rust, `local-ci`). No progress
  page and no disc build. The repo's `CLAUDE.md` states this override.

## Notes

- Windows NTFS is the first target, but this machine has no Windows: NTFS hole-punching
  tests need a Windows PC or VM (`win-sandbox`). Say when they couldn't run.
- Self-merge once `local-ci` passes (workspace default).
