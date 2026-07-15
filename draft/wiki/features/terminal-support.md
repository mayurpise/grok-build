---
type: Feature
title: "Terminal support (product feature)"
description: >
  Open when changing terminal capability detection.
resource: "crates/codegen/xai-grok-pager/docs/user-guide/21-terminal-support.md"
tags: [feature, user-guide]
timestamp: "2026-07-15T23:15:13Z"
x-grounded-paths: ["crates/codegen/xai-grok-pager/docs/user-guide/21-terminal-support.md", "crates/codegen/xai-grok-pager/docs/user-guide/README.md", "README.md"]
x-hotspot-score: 0.4
x-callers: ["systems/xai-grok-pager.md"]
---

# Terminal support (product feature)

## What it is

Product feature documented in the Grok Build user guide (`21-terminal-support.md`).

Grok Build runs as a full-screen TUI. To draw the interface, it relies on terminal escape sequences for color, clipboard, mouse, and full-screen control. Some terminals, multiplexers, and SSH sessions handle these sequences differently. ```bash export COLORTERM=truecolor ``` Inside tmux or over SSH, also add to your tmux config: ```tmux set -g default-terminal "tmux-256color" set -as terminal-features ",*:RGB"

Implementation spans pager UI and/or shell runtime depending on the surface.

## How it works

User-facing behavior is specified in the guide; code typically lives under `xai-grok-pager` (UI) and `xai-grok-shell` / related crates (runtime).

Related crates: `xai-grok-pager`, `xai-grok-shell`.

```mermaid
flowchart LR
  User --> Feature["Terminal support"]
  Feature --> Pager[xai-grok-pager]
  Feature --> Shell[xai-grok-shell]
  Feature --> Guide["user-guide/21-terminal-support.md"]
```

## Used by

- End users of the `grok` CLI/TUI
- Agents implementing or debugging this capability
- [systems/xai-grok-pager.md](../systems/xai-grok-pager.md)
- [systems/xai-grok-shell.md](../systems/xai-grok-shell.md)
- User guide: `crates/codegen/xai-grok-pager/docs/user-guide/21-terminal-support.md`

## Blast radius

Regressions here break the documented user workflow for **Terminal support**. Prefer guide + integration tests in pager/shell when changing behavior.

## See also

- [systems/xai-grok-pager.md](../systems/xai-grok-pager.md)
- [systems/xai-grok-shell.md](../systems/xai-grok-shell.md)
- User guide: `crates/codegen/xai-grok-pager/docs/user-guide/21-terminal-support.md`
