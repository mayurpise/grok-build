---
type: Module
title: "xai-grok-paths — Workspace crate"
description: >
  Open when changing the `xai-grok-paths` crate at `crates/codegen/xai-grok-paths`.
resource: "crates/codegen/xai-grok-paths"
tags: [crate, crates-codegen, rust]
timestamp: "2026-07-15T23:15:13Z"
x-grounded-paths: ["crates/codegen/xai-grok-paths/src/lib.rs", "crates/codegen/xai-grok-paths/Cargo.toml", "README.md"]
x-hotspot-score: 0.4
x-callers: ["systems/codegen.md"]
---

# xai-grok-paths — Workspace crate

## What it is

`xai-grok-paths` is a Cargo workspace member at `crates/codegen/xai-grok-paths` (1 `.rs` files).

Type-safe path wrappers for absolute and relative UTF-8 paths.

**Role:** Workspace crate. [Graph: approximate via crate tree; Human:Synthesis from lib.rs docs]

## How it works

Primary surface is `src/lib.rs`.

Notable workspace dependencies (from crate Cargo.toml, truncated): `camino`, `serde`, `thiserror`.

```mermaid
flowchart TB
  C["xai-grok-paths"]
  C --> Leaf["leaf / few internal deps"]
```

## Used by

- Parent cluster: [codegen](codegen.md)
- Other crates that depend on this package (see Cargo graph / `cargo tree -p xai-grok-paths`)

## Blast radius

Changes affect any consumer of `xai-grok-paths` in the workspace. Run `cargo test -p xai-grok-paths` and re-check dependent top crates (`xai-grok-shell`, `xai-grok-pager`, `xai-grok-tools`) when public APIs move.

## See also

- [systems/codegen.md](codegen.md)
- [entrypoint](../entrypoints/main.md)
- Workspace root `Cargo.toml` (generated — do not hand-edit)

## Notes

- Prefer `cargo check -p xai-grok-paths` / `cargo test -p xai-grok-paths` for this crate.
- Full workspace builds are slow; target the crate under change.
- See root README for build prerequisites (Rust toolchain, protoc).
