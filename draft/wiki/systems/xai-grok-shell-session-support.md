---
type: Module
title: "xai-grok-shell-session-support — Workspace crate"
description: >
  Open when changing the `xai-grok-shell-session-support` crate at `crates/codegen/xai-grok-shell-session-support`.
resource: "crates/codegen/xai-grok-shell-session-support"
tags: [crate, crates-codegen, rust]
timestamp: "2026-07-15T23:15:13Z"
x-grounded-paths: ["crates/codegen/xai-grok-shell-session-support/src/lib.rs", "crates/codegen/xai-grok-shell-session-support/Cargo.toml", "README.md"]
x-hotspot-score: 0.4
x-callers: ["systems/codegen.md"]
---

# xai-grok-shell-session-support — Workspace crate

## What it is

`xai-grok-shell-session-support` is a Cargo workspace member at `crates/codegen/xai-grok-shell-session-support` (2 `.rs` files).

Session-support modules extracted from `xai-grok-shell`'s `session/` tree (which re-exports them at their original paths) so they build in parallel and stop rebuilding on shell edits.

**Role:** Workspace crate. [Graph: approximate via crate tree; Human:Synthesis from lib.rs docs]

## How it works

Primary surface is `src/lib.rs`.

Notable workspace dependencies (from crate Cargo.toml, truncated): `agent-client-protocol`, `chrono`, `reqwest`, `serde`, `serde_json`, `thiserror`, `tokio`, `tokio-util`.

```mermaid
flowchart TB
  C["xai-grok-shell-session-support"]
  D0["xai-file-utils"]
  C --> D0
  D1["xai-grok-http"]
  C --> D1
  D2["xai-grok-shell-base"]
  C --> D2
```

## Used by

- Parent cluster: [codegen](codegen.md)
- Other crates that depend on this package (see Cargo graph / `cargo tree -p xai-grok-shell-session-support`)

## Blast radius

Changes affect any consumer of `xai-grok-shell-session-support` in the workspace. Run `cargo test -p xai-grok-shell-session-support` and re-check dependent top crates (`xai-grok-shell`, `xai-grok-pager`, `xai-grok-tools`) when public APIs move.

## See also

- [systems/codegen.md](codegen.md)
- [entrypoint](../entrypoints/main.md)
- Workspace root `Cargo.toml` (generated — do not hand-edit)
