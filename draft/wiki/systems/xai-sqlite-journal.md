---
type: Module
title: "xai-sqlite-journal — Workspace crate"
description: >
  Open when changing the `xai-sqlite-journal` crate at `crates/codegen/xai-sqlite-journal`.
resource: "crates/codegen/xai-sqlite-journal"
tags: [crate, crates-codegen, rust]
timestamp: "2026-07-15T23:15:13Z"
x-grounded-paths: ["crates/codegen/xai-sqlite-journal/src/lib.rs", "crates/codegen/xai-sqlite-journal/Cargo.toml", "README.md"]
x-hotspot-score: 0.4
x-callers: ["systems/codegen.md"]
---

# xai-sqlite-journal — Workspace crate

## What it is

`xai-sqlite-journal` is a Cargo workspace member at `crates/codegen/xai-sqlite-journal` (1 `.rs` files).

Filesystem-aware SQLite journal-mode selection.  WAL keeps its wal-index in an mmap'd `-shm` file and relies on coherent shared memory plus reliable POSIX locks — guarantees network filesystems do not provide. When `$HOME` (and thus `~/.grok`) is NFS-mounted on several machines at once, a peer host truncating/rebuilding the `-shm` during WAL recovery or close rips the backing out from under our ma

**Role:** Workspace crate. [Graph: approximate via crate tree; Human:Synthesis from lib.rs docs]

## How it works

Primary surface is `src/lib.rs`.

Notable workspace dependencies (from crate Cargo.toml, truncated): `rusqlite`, `tracing`.

```mermaid
flowchart TB
  C["xai-sqlite-journal"]
  C --> Leaf["leaf / few internal deps"]
```

## Used by

- Parent cluster: [codegen](codegen.md)
- Other crates that depend on this package (see Cargo graph / `cargo tree -p xai-sqlite-journal`)

## Blast radius

Changes affect any consumer of `xai-sqlite-journal` in the workspace. Run `cargo test -p xai-sqlite-journal` and re-check dependent top crates (`xai-grok-shell`, `xai-grok-pager`, `xai-grok-tools`) when public APIs move.

## See also

- [systems/codegen.md](codegen.md)
- [entrypoint](../entrypoints/main.md)
- Workspace root `Cargo.toml` (generated — do not hand-edit)

## Notes

- Prefer `cargo check -p xai-sqlite-journal` / `cargo test -p xai-sqlite-journal` for this crate.
- Full workspace builds are slow; target the crate under change.
- See root README for build prerequisites (Rust toolchain, protoc).
