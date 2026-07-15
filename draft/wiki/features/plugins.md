---
type: Feature
title: "Plugins (product feature)"
description: >
  Open when changing plugin load/install.
resource: "crates/codegen/xai-grok-pager/docs/user-guide/09-plugins.md"
tags: [feature, user-guide]
timestamp: "2026-07-15T23:15:13Z"
x-grounded-paths: ["crates/codegen/xai-grok-pager/docs/user-guide/09-plugins.md", "crates/codegen/xai-grok-pager/docs/user-guide/README.md", "README.md"]
x-hotspot-score: 0.4
x-callers: ["systems/xai-grok-pager.md"]
---

# Plugins (product feature)

## What it is

Product feature documented in the Grok Build user guide (`09-plugins.md`).

A plugin bundles skills, slash commands, agents, hooks, MCP server configurations, and LSP server configurations into one installable unit. --- A plugin is a directory that holds any combination of these components: - **Skills** -- a `skills/` directory of SKILL.md files - **Slash commands** -- a `commands/` directory of command files - **Agents** -- an `agents/` directory of agent definitions - **Hooks** -- a `hooks/hooks.json` file of lifecycle hooks. Plugin hooks also receive `GROK_PLUGIN_ROO

Implementation spans pager UI and/or shell runtime depending on the surface.

## How it works

User-facing behavior is specified in the guide; code typically lives under `xai-grok-pager` (UI) and `xai-grok-shell` / related crates (runtime).

Related crates: `xai-grok-pager`, `xai-grok-shell`.

```mermaid
flowchart LR
  User --> Feature["Plugins"]
  Feature --> Pager[xai-grok-pager]
  Feature --> Shell[xai-grok-shell]
  Feature --> Guide["user-guide/09-plugins.md"]
```

## Used by

- End users of the `grok` CLI/TUI
- Agents implementing or debugging this capability
- [systems/xai-grok-pager.md](../systems/xai-grok-pager.md)
- [systems/xai-grok-shell.md](../systems/xai-grok-shell.md)
- User guide: `crates/codegen/xai-grok-pager/docs/user-guide/09-plugins.md`

## Blast radius

Regressions here break the documented user workflow for **Plugins**. Prefer guide + integration tests in pager/shell when changing behavior.

## See also

- [systems/xai-grok-pager.md](../systems/xai-grok-pager.md)
- [systems/xai-grok-shell.md](../systems/xai-grok-shell.md)
- User guide: `crates/codegen/xai-grok-pager/docs/user-guide/09-plugins.md`
