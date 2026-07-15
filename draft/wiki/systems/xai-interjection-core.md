---
type: Module
title: "xai-interjection-core — Workspace crate"
description: >
  Open when changing the `xai-interjection-core` crate at `crates/common/xai-interjection-core`.
resource: "crates/common/xai-interjection-core"
tags: [crate, crates-common, rust]
timestamp: "2026-07-15T23:15:13Z"
x-grounded-paths: ["crates/common/xai-interjection-core/src/lib.rs", "crates/common/xai-interjection-core/Cargo.toml", "README.md"]
x-hotspot-score: 0.4
x-callers: ["systems/common.md"]
---

# xai-interjection-core — Workspace crate

## What it is

`xai-interjection-core` is a Cargo workspace member at `crates/common/xai-interjection-core` (4 `.rs` files).

Rust crate `xai-interjection-core` at `crates/common/xai-interjection-core`.

**Role:** Workspace crate. [Graph: approximate via crate tree; Human:Synthesis from lib.rs docs]

## How it works

Primary surface is `src/lib.rs`.

Notable workspace dependencies (from crate Cargo.toml, truncated): `serde`.

```mermaid
flowchart TB
  C["xai-interjection-core"]
  C --> Leaf["leaf / few internal deps"]
```

## Used by

- Parent cluster: [common](common.md)
- Other crates that depend on this package (see Cargo graph / `cargo tree -p xai-interjection-core`)

## Blast radius

Changes affect any consumer of `xai-interjection-core` in the workspace. Run `cargo test -p xai-interjection-core` and re-check dependent top crates (`xai-grok-shell`, `xai-grok-pager`, `xai-grok-tools`) when public APIs move.

## See also

- [systems/common.md](common.md)
- [entrypoint](../entrypoints/main.md)
- Workspace root `Cargo.toml` (generated — do not hand-edit)

## Notes

- Prefer `cargo check -p xai-interjection-core` / `cargo test -p xai-interjection-core` for this crate.
- Full workspace builds are slow; target the crate under change.
- See root README for build prerequisites (Rust toolchain, protoc).
