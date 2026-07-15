---
type: Feature
title: "Slash commands (product feature)"
description: >
  Open when adding or changing /commands in the TUI.
resource: "crates/codegen/xai-grok-pager/docs/user-guide/04-slash-commands.md"
tags: [feature, user-guide]
timestamp: "2026-07-15T23:15:13Z"
x-grounded-paths: ["crates/codegen/xai-grok-pager/docs/user-guide/04-slash-commands.md", "crates/codegen/xai-grok-pager/docs/user-guide/README.md", "README.md"]
x-hotspot-score: 0.4
x-callers: ["systems/xai-grok-pager.md"]
---

# Slash commands (product feature)

## What it is

Product feature documented in the Grok Build user guide (`04-slash-commands.md`).

Type `/` in the prompt to access commands. Each command runs an action immediately and autocompletes as you type. Slash commands come from two sources: - **Shell builtins** -- handled by the agent backend (xai-grok-shell) - **Pager builtins** -- handled by the TUI frontend (xai-grok-pager) Both sets are available in the autocomplete menu. Skills installed via SKILL.md files also appear as slash commands. --- Start a new session, clearing the current conversation. ```

Implementation spans pager UI and/or shell runtime depending on the surface.

## How it works

User-facing behavior is specified in the guide; code typically lives under `xai-grok-pager` (UI) and `xai-grok-shell` / related crates (runtime).

Related crates: `xai-grok-pager`.

```mermaid
flowchart LR
  User --> Feature["Slash commands"]
  Feature --> Pager[xai-grok-pager]
  Feature --> Shell[xai-grok-shell]
  Feature --> Guide["user-guide/04-slash-commands.md"]
```

## Used by

- End users of the `grok` CLI/TUI
- Agents implementing or debugging this capability
- [systems/xai-grok-pager.md](../systems/xai-grok-pager.md)
- User guide: `crates/codegen/xai-grok-pager/docs/user-guide/04-slash-commands.md`

## Blast radius

Regressions here break the documented user workflow for **Slash commands**. Prefer guide + integration tests in pager/shell when changing behavior.

## See also

- [systems/xai-grok-pager.md](../systems/xai-grok-pager.md)
- User guide: `crates/codegen/xai-grok-pager/docs/user-guide/04-slash-commands.md`
