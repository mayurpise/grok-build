---
type: Module
title: "xai-grok-hooks — Hooks runtime"
description: >
  Open when changing PreToolUse/session hooks discovery or execution.
resource: "crates/codegen/xai-grok-hooks"
tags: [crate, crates-codegen, rust]
timestamp: "2026-07-15T23:15:13Z"
x-grounded-paths: ["crates/codegen/xai-grok-hooks/src/lib.rs", "crates/codegen/xai-grok-hooks/Cargo.toml", "README.md"]
x-hotspot-score: 0.4
x-callers: ["systems/codegen.md"]
---

# xai-grok-hooks — Hooks runtime

## What it is

`xai-grok-hooks` is a Cargo workspace member at `crates/codegen/xai-grok-hooks` (15 `.rs` files).

# xai-grok-hooks  Runtime hook system for Grok — file-based discovery, command execution, and policy enforcement.  ## Overview  This crate provides a minimal hooks system for Grok. Hooks are discovered from dedicated directories (`~/.grok/hooks/` and `<git-worktree-root>/.grok/hooks/`), defined in JSON files (compatible settings format), and executed as child processes.  ## v0 scope  - Four event 

**Role:** Hooks runtime. [Graph: approximate via crate tree; Human:Synthesis from lib.rs docs]

## How it works

Primary surface is `src/lib.rs`.

Notable workspace dependencies (from crate Cargo.toml, truncated): `fastrand`, `regex`, `reqwest`, `serde`, `serde_json`, `shellexpand`, `thiserror`, `tokio`.

```mermaid
flowchart TB
  C["xai-grok-hooks"]
  D0["xai-grok-config"]
  C --> D0
  D1["xai-grok-tools"]
  C --> D1
```

## Used by

- Parent cluster: [codegen](codegen.md)
- Other crates that depend on this package (see Cargo graph / `cargo tree -p xai-grok-hooks`)

## Blast radius

Changes affect any consumer of `xai-grok-hooks` in the workspace. Run `cargo test -p xai-grok-hooks` and re-check dependent top crates (`xai-grok-shell`, `xai-grok-pager`, `xai-grok-tools`) when public APIs move.

## See also

- [systems/codegen.md](codegen.md)
- [entrypoint](../entrypoints/main.md)
- Workspace root `Cargo.toml` (generated — do not hand-edit)
