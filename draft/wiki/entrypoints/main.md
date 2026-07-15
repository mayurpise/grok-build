---
type: Entrypoint
title: "xai-grok-pager binary (grok CLI)"
description: >
  Open when changing CLI startup, mode dispatch (TUI/headless/agent/leader), auto-update, jemalloc, or composition-root wiring between pager and shell.
resource: "crates/codegen/xai-grok-pager-bin/src/main.rs"
tags: [entrypoint, cli, binary]
timestamp: "2026-07-15T23:06:40Z"
x-grounded-paths: ["crates/codegen/xai-grok-pager-bin/src/main.rs", "crates/codegen/xai-grok-pager-bin/Cargo.toml", "crates/codegen/xai-grok-shell/src/agent/app.rs", "README.md"]
x-hotspot-score: 0.5
x-callers: []
---

# xai-grok-pager binary (grok CLI)

## What it is


Composition-root package `xai-grok-pager-bin` builds binary **`xai-grok-pager`** (distributed as `grok`). Owns global allocator (optional jemalloc), CLI parsing via pager args, auto-update enforcement, and dispatch into TUI vs shell agent modes. [Graph:High; Existing:README.md]

Provenance: graph package inventory + repository layout synthesis. Agents should open grounded paths rather than treat this page as complete implementation documentation.

## How it works

```mermaid
flowchart TB
  main[main.rs] --> Parse[PagerArgs / Command]
  Parse -->|interactive| TUI[xai-grok-pager app]
  Parse -->|headless -p| Headless[run_headless]
  Parse -->|agent stdio| Stdio[run_stdio_agent]
  Parse -->|leader| Leader[run_leader]
  Parse -->|workspace mgmt| WS[WorkspaceMgmtCommand]
  main --> Update[xai-grok-update auto_update]
  TUI --> Shell[xai-grok-shell session]
  Headless --> Shell
  Stdio --> ACP[ACP gateway]
```

Key shell entrypoints: `run_headless`, `run_stdio_agent`, `run_leader` in `xai-grok-shell/src/agent/app.rs`.

## Used by

- End-user installs (`curl …/install.sh`)
- Developers: `cargo run -p xai-grok-pager-bin`
- IDE ACP clients spawning `grok agent stdio`

## Blast radius

Startup regressions block all modes. Mode-dispatch mistakes can skip auth, bypass update gates, or fail to attach leader sockets. Always smoke-test interactive + `grok -p` headless after changes.

## See also

- [codegen](../systems/codegen.md)
- User guide getting started: `crates/codegen/xai-grok-pager/docs/user-guide/01-getting-started.md`
