---
type: Feature
title: "Skills (product feature)"
description: >
  Open when changing skill discovery or skill tools.
resource: "crates/codegen/xai-grok-pager/docs/user-guide/08-skills.md"
tags: [feature, user-guide]
timestamp: "2026-07-15T23:15:13Z"
x-grounded-paths: ["crates/codegen/xai-grok-pager/docs/user-guide/08-skills.md", "crates/codegen/xai-grok-pager/docs/user-guide/README.md", "README.md"]
x-hotspot-score: 0.4
x-callers: ["systems/xai-grok-pager.md"]
---

# Skills (product feature)

## What it is

Product feature documented in the Grok Build user guide (`08-skills.md`).

Skills are reusable prompt packages that extend Grok with task-specific instructions. They let you capture a repeatable procedure once, instead of re-explaining it each session. --- A skill is a directory that contains a `SKILL.md` file. Its markdown body tells Grok how to handle a specific type of task: step-by-step instructions, conventions, and tool-usage patterns. Use a skill for a repeatable procedure that's too specific for AGENTS.md but too long to retype. Grok activates a skill only when

Implementation spans pager UI and/or shell runtime depending on the surface.

## How it works

User-facing behavior is specified in the guide; code typically lives under `xai-grok-pager` (UI) and `xai-grok-shell` / related crates (runtime).

Related crates: `xai-grok-tools`.

```mermaid
flowchart LR
  User --> Feature["Skills"]
  Feature --> Pager[xai-grok-pager]
  Feature --> Shell[xai-grok-shell]
  Feature --> Guide["user-guide/08-skills.md"]
```

## Used by

- End users of the `grok` CLI/TUI
- Agents implementing or debugging this capability
- [systems/xai-grok-tools.md](../systems/xai-grok-tools.md)
- User guide: `crates/codegen/xai-grok-pager/docs/user-guide/08-skills.md`

## Blast radius

Regressions here break the documented user workflow for **Skills**. Prefer guide + integration tests in pager/shell when changing behavior.

## See also

- [systems/xai-grok-tools.md](../systems/xai-grok-tools.md)
- User guide: `crates/codegen/xai-grok-pager/docs/user-guide/08-skills.md`
