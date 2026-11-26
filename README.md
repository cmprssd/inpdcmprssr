# inpdcmprssr

In-place decompressor. Extracts a compressed file and deletes the parts of it it has already
read as it goes, so extracting doesn't need disk space for both the archive and its output.
A Rust library crate plus a small CLI. Formats: zstd, gzip, ZIP. Windows NTFS first.

Status: not built yet; see [docs/BRIEF.md](docs/BRIEF.md).

Licensed under MIT or Apache-2.0, at your option.
