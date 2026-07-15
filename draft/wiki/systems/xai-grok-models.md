---
type: Module
title: "xai-grok-models — Model catalog"
description: >
  Open when changing default model lists.
resource: "crates/codegen/xai-grok-models"
tags: [crate, crates-codegen, rust]
timestamp: "2026-07-15T23:15:13Z"
x-grounded-paths: ["crates/codegen/xai-grok-models/src/lib.rs", "crates/codegen/xai-grok-models/Cargo.toml", "README.md"]
x-hotspot-score: 0.4
x-callers: ["systems/codegen.md"]
---

# xai-grok-models — Model catalog

## What it is

`xai-grok-models` is a Cargo workspace member at `crates/codegen/xai-grok-models` (1 `.rs` files).

Default model IDs loaded from `default_models.json` at runtime. Edit that JSON file to change them.  At runtime each model is resolved via: CLI flag > ENV var > config.toml > remote settings > these defaults

**Role:** Model catalog. [Graph: approximate via crate tree; Human:Synthesis from lib.rs docs]

## How it works

Primary surface is `src/lib.rs`.

Notable workspace dependencies (from crate Cargo.toml, truncated): `serde`, `serde_json`.

```mermaid
flowchart TB
  C["xai-grok-models"]
  C --> Leaf["leaf / few internal deps"]
```

## Used by

- Parent cluster: [codegen](codegen.md)
- Other crates that depend on this package (see Cargo graph / `cargo tree -p xai-grok-models`)

## Blast radius

Changes affect any consumer of `xai-grok-models` in the workspace. Run `cargo test -p xai-grok-models` and re-check dependent top crates (`xai-grok-shell`, `xai-grok-pager`, `xai-grok-tools`) when public APIs move.

## See also

- [systems/codegen.md](codegen.md)
- [entrypoint](../entrypoints/main.md)
- Workspace root `Cargo.toml` (generated — do not hand-edit)

## Notes

- Prefer `cargo check -p xai-grok-models` / `cargo test -p xai-grok-models` for this crate.
- Full workspace builds are slow; target the crate under change.
- See root README for build prerequisites (Rust toolchain, protoc).
