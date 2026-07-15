---
type: Module
title: "xai-grok-pager — Full-screen TUI"
description: >
  Open when changing TUI scrollback, prompt, slash commands, modals, event loop, or pager UI.
resource: "crates/codegen/xai-grok-pager"
tags: [crate, crates-codegen, rust]
timestamp: "2026-07-15T23:15:13Z"
x-grounded-paths: ["crates/codegen/xai-grok-pager/src/lib.rs", "crates/codegen/xai-grok-pager/Cargo.toml", "README.md"]
x-hotspot-score: 0.4
x-callers: ["systems/codegen.md"]
---

# xai-grok-pager — Full-screen TUI

## What it is

`xai-grok-pager` is a Cargo workspace member at `crates/codegen/xai-grok-pager` (596 `.rs` files).

xai-grok-pager — Grok Build TUI.  A clean-room implementation built on the v3 pager rendering engine.

**Role:** Full-screen TUI. [Graph: approximate via crate tree; Human:Synthesis from lib.rs docs]

## How it works

Primary surface is `src/lib.rs`.

Notable workspace dependencies (from crate Cargo.toml, truncated): `dunce`, `xai-tty-utils`, `xai-grok-version`, `xai-prompt-queue`, `xai-grok-pager-render`, `ratatui`, `xai-grok-announcements`, `crossterm`.

```mermaid
flowchart TB
  C["xai-grok-pager"]
  D0["xai-tty-utils"]
  C --> D0
  D1["xai-grok-version"]
  C --> D1
  D2["xai-prompt-queue"]
  C --> D2
  D3["xai-grok-pager-render"]
  C --> D3
  D4["xai-grok-announcements"]
  C --> D4
```

## Used by

- Parent cluster: [codegen](codegen.md)
- Other crates that depend on this package (see Cargo graph / `cargo tree -p xai-grok-pager`)

## Blast radius

Changes affect any consumer of `xai-grok-pager` in the workspace. Run `cargo test -p xai-grok-pager` and re-check dependent top crates (`xai-grok-shell`, `xai-grok-pager`, `xai-grok-tools`) when public APIs move.

## See also

- [systems/codegen.md](codegen.md)
- [entrypoint](../entrypoints/main.md)
- Workspace root `Cargo.toml` (generated — do not hand-edit)
