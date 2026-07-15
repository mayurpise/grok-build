---
type: Module
title: "xai-grok-shell-base — Shell base helpers"
description: >
  Open when changing CPU profile, env helpers shared by shell.
resource: "crates/codegen/xai-grok-shell-base"
tags: [crate, crates-codegen, rust]
timestamp: "2026-07-15T23:15:13Z"
x-grounded-paths: ["crates/codegen/xai-grok-shell-base/src/lib.rs", "crates/codegen/xai-grok-shell-base/Cargo.toml", "README.md"]
x-hotspot-score: 0.4
x-callers: ["systems/codegen.md"]
---

# xai-grok-shell-base — Shell base helpers

## What it is

`xai-grok-shell-base` is a Cargo workspace member at `crates/codegen/xai-grok-shell-base` (10 `.rs` files).

Foundation modules shared by the grok shell crate family. Extracted from `xai-grok-shell` (which re-exports them at their original paths) so they build in parallel and stop rebuilding on shell edits.

**Role:** Shell base helpers. [Graph: approximate via crate tree; Human:Synthesis from lib.rs docs]

## How it works

Primary surface is `src/lib.rs`.

Notable workspace dependencies (from crate Cargo.toml, truncated): `anyhow`, `chrono`, `reqwest`, `serde`, `serde_json`, `thiserror`, `tokio`, `tracing`.

```mermaid
flowchart TB
  C["xai-grok-shell-base"]
  D0["xai-grok-config"]
  C --> D0
  D1["xai-grok-env"]
  C --> D1
  D2["xai-grok-shared"]
  C --> D2
```

## Used by

- Parent cluster: [codegen](codegen.md)
- Other crates that depend on this package (see Cargo graph / `cargo tree -p xai-grok-shell-base`)

## Blast radius

Changes affect any consumer of `xai-grok-shell-base` in the workspace. Run `cargo test -p xai-grok-shell-base` and re-check dependent top crates (`xai-grok-shell`, `xai-grok-pager`, `xai-grok-tools`) when public APIs move.

## See also

- [systems/codegen.md](codegen.md)
- [entrypoint](../entrypoints/main.md)
- Workspace root `Cargo.toml` (generated — do not hand-edit)
