---
type: Module
title: "xai-grok-plugin-marketplace — Plugin marketplace"
description: >
  Open when changing plugin discovery/install marketplace.
resource: "crates/codegen/xai-grok-plugin-marketplace"
tags: [crate, crates-codegen, rust]
timestamp: "2026-07-15T23:15:13Z"
x-grounded-paths: ["crates/codegen/xai-grok-plugin-marketplace/src/lib.rs", "crates/codegen/xai-grok-plugin-marketplace/Cargo.toml", "README.md"]
x-hotspot-score: 0.4
x-callers: ["systems/codegen.md"]
---

# xai-grok-plugin-marketplace — Plugin marketplace

## What it is

`xai-grok-plugin-marketplace` is a Cargo workspace member at `crates/codegen/xai-grok-plugin-marketplace` (11 `.rs` files).

Plugin marketplace browse and index crate.  Provides marketplace source configuration, plugin discovery (indexed + filesystem fallback), and install integration with the existing `InstallRegistry` pipeline.

**Role:** Plugin marketplace. [Graph: approximate via crate tree; Human:Synthesis from lib.rs docs]

## How it works

Primary surface is `src/lib.rs`.

Notable workspace dependencies (from crate Cargo.toml, truncated): `dirs`, `dunce`, `fs2`, `git2`, `serde`, `serde_json`, `thiserror`, `toml`.

```mermaid
flowchart TB
  C["xai-grok-plugin-marketplace"]
  D0["xai-tty-utils"]
  C --> D0
  D1["xai-grok-agent"]
  C --> D1
```

## Used by

- Parent cluster: [codegen](codegen.md)
- Other crates that depend on this package (see Cargo graph / `cargo tree -p xai-grok-plugin-marketplace`)

## Blast radius

Changes affect any consumer of `xai-grok-plugin-marketplace` in the workspace. Run `cargo test -p xai-grok-plugin-marketplace` and re-check dependent top crates (`xai-grok-shell`, `xai-grok-pager`, `xai-grok-tools`) when public APIs move.

## See also

- [systems/codegen.md](codegen.md)
- [entrypoint](../entrypoints/main.md)
- Workspace root `Cargo.toml` (generated — do not hand-edit)
