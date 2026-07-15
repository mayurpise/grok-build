---
type: Module
title: "xai-tool-types — Tool type defs"
description: >
  Open when changing shared tool types.
resource: "crates/common/xai-tool-types"
tags: [crate, crates-common, rust]
timestamp: "2026-07-15T23:15:13Z"
x-grounded-paths: ["crates/common/xai-tool-types/src/lib.rs", "crates/common/xai-tool-types/Cargo.toml", "README.md"]
x-hotspot-score: 0.4
x-callers: ["systems/common.md"]
---

# xai-tool-types — Tool type defs

## What it is

`xai-tool-types` is a Cargo workspace member at `crates/common/xai-tool-types` (6 `.rs` files).

Canonical, extensible tool types.

**Role:** Tool type defs. [Graph: approximate via crate tree; Human:Synthesis from lib.rs docs]

## How it works

Primary surface is `src/lib.rs`.

Notable workspace dependencies (from crate Cargo.toml, truncated): `minijinja`, `schemars`, `serde`, `serde_json`.

```mermaid
flowchart TB
  C["xai-tool-types"]
  C --> Leaf["leaf / few internal deps"]
```

## Used by

- Parent cluster: [common](common.md)
- Other crates that depend on this package (see Cargo graph / `cargo tree -p xai-tool-types`)

## Blast radius

Changes affect any consumer of `xai-tool-types` in the workspace. Run `cargo test -p xai-tool-types` and re-check dependent top crates (`xai-grok-shell`, `xai-grok-pager`, `xai-grok-tools`) when public APIs move.

## See also

- [systems/common.md](common.md)
- [entrypoint](../entrypoints/main.md)
- Workspace root `Cargo.toml` (generated — do not hand-edit)

## Notes

- Prefer `cargo check -p xai-tool-types` / `cargo test -p xai-tool-types` for this crate.
- Full workspace builds are slow; target the crate under change.
- See root README for build prerequisites (Rust toolchain, protoc).
