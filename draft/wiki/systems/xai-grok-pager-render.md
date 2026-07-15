---
type: Module
title: "xai-grok-pager-render — Pager render engine"
description: >
  Open when changing terminal rendering, themes, or scrollback paint paths.
resource: "crates/codegen/xai-grok-pager-render"
tags: [crate, crates-codegen, rust]
timestamp: "2026-07-15T23:15:13Z"
x-grounded-paths: ["crates/codegen/xai-grok-pager-render/src/lib.rs", "crates/codegen/xai-grok-pager-render/Cargo.toml", "README.md"]
x-hotspot-score: 0.4
x-callers: ["systems/codegen.md"]
---

# xai-grok-pager-render — Pager render engine

## What it is

`xai-grok-pager-render` is a Cargo workspace member at `crates/codegen/xai-grok-pager-render` (64 `.rs` files).

Rust crate `xai-grok-pager-render` at `crates/codegen/xai-grok-pager-render`.

**Role:** Pager render engine. [Graph: approximate via crate tree; Human:Synthesis from lib.rs docs]

## How it works

Primary surface is `src/lib.rs`.

Notable workspace dependencies (from crate Cargo.toml, truncated): `dunce`, `xai-tty-utils`, `ratatui`, `ratatui-core`, `crossterm`, `textwrap`, `regex`, `unicode-width`.

```mermaid
flowchart TB
  C["xai-grok-pager-render"]
  D0["xai-tty-utils"]
  C --> D0
  D1["xai-grok-markdown"]
  C --> D1
```

## Used by

- Parent cluster: [codegen](codegen.md)
- Other crates that depend on this package (see Cargo graph / `cargo tree -p xai-grok-pager-render`)

## Blast radius

Changes affect any consumer of `xai-grok-pager-render` in the workspace. Run `cargo test -p xai-grok-pager-render` and re-check dependent top crates (`xai-grok-shell`, `xai-grok-pager`, `xai-grok-tools`) when public APIs move.

## See also

- [systems/codegen.md](codegen.md)
- [entrypoint](../entrypoints/main.md)
- Workspace root `Cargo.toml` (generated — do not hand-edit)
