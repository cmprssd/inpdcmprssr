# Decisions

Dated entries: question, choice, reason. Newest at the bottom.

## 2026-11-11 (from the backlog brief)

- **Build on HatchZip or our own engine?** → Our own. User's choice, made knowing HatchZip exists (it lacks `.tar.zst`; its design is a reference).
- **Owner and name?** → `cmprssd/inpdcmprssr`. Abbreviated like the other cmprssd repos (the cmprssd naming exception).
- **Form?** → A Rust library crate plus a small CLI, in its own repo. The cmprssd engines depend on the crate.
- **Where does cmprssd use it?** → Installing a game from a compressed package or disc copy, not converting the game's own install.
- **First formats?** → zstd (`.tar.zst`, `.zst`), gzip (`.tar.gz`, `.gz`) and ZIP. Covers the engines' packages and common archives.
- **First platform?** → Windows NTFS (sparse files, `FSCTL_SET_ZERO_DATA`), then Linux. The games run on Windows.
- **Crash safety in v1?** → Yes: journal, flush output before every free, resume, kill tests. An interrupted run otherwise destroys data.
- **Archive and output on different drives?** → Extract normally without freeing, and say so. Nothing to gain by freeing.
- **Which cmprssd org rules apply?** → Only the shared tooling (Rust, `local-ci`). No progress page, no disc build: this is a library, not a game engine.
- **Licence?** → MIT or Apache-2.0 (dual, the Rust convention).
- **Not doing?** → No GUI, no compression, no RAR or 7z, no encrypted archives.
- **Policy check?** → Allowed: a local file utility; uses no Anthropic services at runtime.

## 2026-11-26 (start)

- **Repo visibility?** → Public, like nfsh and swjkja. User's choice.
- **Key consumer?** → nfsh (`cmprssd/nfsh`), named by the user as where this is most useful: its packages are large. Its install flow is the first real integration target.
- **Policy recheck?** → Still allowed (Usage Policy effective 2026-11-12).
