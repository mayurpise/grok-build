---
type: Feature
title: "Permissions and safety (product feature)"
description: >
  Open when changing permission rules, modes, or dangerous-command policy.
resource: "crates/codegen/xai-grok-pager/docs/user-guide/22-permissions-and-safety.md"
tags: [feature, user-guide]
timestamp: "2026-07-15T23:15:13Z"
x-grounded-paths: ["crates/codegen/xai-grok-pager/docs/user-guide/22-permissions-and-safety.md", "crates/codegen/xai-grok-pager/docs/user-guide/README.md", "README.md"]
x-hotspot-score: 0.4
x-callers: ["systems/xai-grok-pager.md"]
---

# Permissions and safety (product feature)

## What it is

Product feature documented in the Grok Build user guide (`22-permissions-and-safety.md`).

Grok can read files, search code, edit files, and run shell commands. The permission system controls what the agent is allowed to do. You can combine several independent layers: permission rules, permission modes, hooks, and the OS-level sandbox. This guide explains how a tool call is authorized, how to configure permission rules from the CLI, native configuration, or Claude settings, and how to use `PreToolUse` hooks for allow lists that apply in every mode. --- When the model requests a tool, 

Implementation spans pager UI and/or shell runtime depending on the surface.

## How it works

User-facing behavior is specified in the guide; code typically lives under `xai-grok-pager` (UI) and `xai-grok-shell` / related crates (runtime).

Related crates: `xai-grok-workspace`, `xai-grok-tools`, `xai-grok-hooks`.

```mermaid
flowchart LR
  User --> Feature["Permissions and safety"]
  Feature --> Pager[xai-grok-pager]
  Feature --> Shell[xai-grok-shell]
  Feature --> Guide["user-guide/22-permissions-and-safety.md"]
```

## Used by

- End users of the `grok` CLI/TUI
- Agents implementing or debugging this capability
- [systems/xai-grok-workspace.md](../systems/xai-grok-workspace.md)
- [systems/xai-grok-tools.md](../systems/xai-grok-tools.md)
- [systems/xai-grok-hooks.md](../systems/xai-grok-hooks.md)
- User guide: `crates/codegen/xai-grok-pager/docs/user-guide/22-permissions-and-safety.md`

## Blast radius

Regressions here break the documented user workflow for **Permissions and safety**. Prefer guide + integration tests in pager/shell when changing behavior.

## See also

- [systems/xai-grok-workspace.md](../systems/xai-grok-workspace.md)
- [systems/xai-grok-tools.md](../systems/xai-grok-tools.md)
- [systems/xai-grok-hooks.md](../systems/xai-grok-hooks.md)
- User guide: `crates/codegen/xai-grok-pager/docs/user-guide/22-permissions-and-safety.md`
