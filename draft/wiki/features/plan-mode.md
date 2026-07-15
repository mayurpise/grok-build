---
type: Feature
title: "Plan mode (product feature)"
description: >
  Open when changing plan-mode workflow.
resource: "crates/codegen/xai-grok-pager/docs/user-guide/19-plan-mode.md"
tags: [feature, user-guide]
timestamp: "2026-07-15T23:15:13Z"
x-grounded-paths: ["crates/codegen/xai-grok-pager/docs/user-guide/19-plan-mode.md", "crates/codegen/xai-grok-pager/docs/user-guide/README.md", "README.md"]
x-hotspot-score: 0.4
x-callers: ["systems/xai-grok-pager.md"]
---

# Plan mode (product feature)

## What it is

Product feature documented in the Grok Build user guide (`19-plan-mode.md`).

Plan mode is a structured planning phase: the agent explores the codebase and designs an implementation approach before writing any code. Use it for tasks with genuine ambiguity about the right approach, where getting your input before coding prevents significant rework. --- When plan mode is active, the agent: 1. Reads and searches the codebase to understand existing patterns and architecture 2. Designs an implementation approach and writes it to the plan file 3. May use `ask_user_question` to 

Implementation spans pager UI and/or shell runtime depending on the surface.

## How it works

User-facing behavior is specified in the guide; code typically lives under `xai-grok-pager` (UI) and `xai-grok-shell` / related crates (runtime).

Related crates: `xai-grok-pager`, `xai-grok-shell`.

```mermaid
flowchart LR
  User --> Feature["Plan mode"]
  Feature --> Pager[xai-grok-pager]
  Feature --> Shell[xai-grok-shell]
  Feature --> Guide["user-guide/19-plan-mode.md"]
```

## Used by

- End users of the `grok` CLI/TUI
- Agents implementing or debugging this capability
- [systems/xai-grok-pager.md](../systems/xai-grok-pager.md)
- [systems/xai-grok-shell.md](../systems/xai-grok-shell.md)
- User guide: `crates/codegen/xai-grok-pager/docs/user-guide/19-plan-mode.md`

## Blast radius

Regressions here break the documented user workflow for **Plan mode**. Prefer guide + integration tests in pager/shell when changing behavior.

## See also

- [systems/xai-grok-pager.md](../systems/xai-grok-pager.md)
- [systems/xai-grok-shell.md](../systems/xai-grok-shell.md)
- User guide: `crates/codegen/xai-grok-pager/docs/user-guide/19-plan-mode.md`
