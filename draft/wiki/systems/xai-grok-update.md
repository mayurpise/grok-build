---
type: Module
title: "xai-grok-update — Auto-update"
description: >
  Open when changing binary update check/install.
resource: "crates/codegen/xai-grok-update"
tags: [crate, crates-codegen, rust]
timestamp: "2026-07-15T23:15:13Z"
x-grounded-paths: ["crates/codegen/xai-grok-update/src/lib.rs", "crates/codegen/xai-grok-update/Cargo.toml", "README.md"]
x-hotspot-score: 0.4
x-callers: ["systems/codegen.md"]
---

# xai-grok-update — Auto-update

## What it is

`xai-grok-update` is a Cargo workspace member at `crates/codegen/xai-grok-update` (15 `.rs` files).

Rust crate `xai-grok-update` at `crates/codegen/xai-grok-update`.

**Role:** Auto-update. [Graph: approximate via crate tree; Human:Synthesis from lib.rs docs]

## How it works

Primary surface is `src/lib.rs`.

Notable workspace dependencies (from crate Cargo.toml, truncated): `anyhow`, `futures`, `indicatif`, `reqwest`, `semver`, `serde`, `serde_json`, `thiserror`.

```mermaid
flowchart TB
  C["xai-grok-update"]
  D0["xai-grok-shell"]
  C --> D0
```

## Used by

- Parent cluster: [codegen](codegen.md)
- Other crates that depend on this package (see Cargo graph / `cargo tree -p xai-grok-update`)

## Blast radius

Changes affect any consumer of `xai-grok-update` in the workspace. Run `cargo test -p xai-grok-update` and re-check dependent top crates (`xai-grok-shell`, `xai-grok-pager`, `xai-grok-tools`) when public APIs move.

## See also

- [systems/codegen.md](codegen.md)
- [entrypoint](../entrypoints/main.md)
- Workspace root `Cargo.toml` (generated — do not hand-edit)

## Notes

- Prefer `cargo check -p xai-grok-update` / `cargo test -p xai-grok-update` for this crate.
- Full workspace builds are slow; target the crate under change.
- See root README for build prerequisites (Rust toolchain, protoc).
