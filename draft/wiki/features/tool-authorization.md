---
type: Feature
title: "Tool authorization pipeline"
description: >
  Open when changing permission rules, modes, PreToolUse hooks, remembered grants, dangerous-command lists, or sandbox interaction with tool execution.
resource: "crates/codegen/xai-grok-workspace/src/permission"
tags: [feature, security, permissions]
timestamp: "2026-07-15T23:06:40Z"
x-grounded-paths: ["crates/codegen/xai-grok-workspace/src/permission/mod.rs", "crates/codegen/xai-grok-workspace/src/permission/policy.rs", "crates/codegen/xai-grok-pager/docs/user-guide/22-permissions-and-safety.md", "README.md"]
x-hotspot-score: 0.5
x-callers: ["systems/codegen.md"]
---

# Tool authorization pipeline

## What it is


End-to-end authorization for model-requested tools and shell commands. Spans hooks, permission rules/modes, remembered grants, built-in read-only auto-approvals, and optional OS sandbox. [Existing:user-guide/22]

Provenance: graph package inventory + repository layout synthesis. Agents should open grounded paths rather than treat this page as complete implementation documentation.

## How it works

```mermaid
sequenceDiagram
  participant Model
  participant Tools as xai-grok-tools
  participant Hooks as PreToolUse hooks
  participant Perm as permission pipeline
  participant Sandbox as OS sandbox
  participant Host
  Model->>Tools: tool call
  Tools->>Hooks: PreToolUse
  alt hook deny
    Hooks-->>Model: denied
  else continue
    Tools->>Perm: rules / grants / mode
    alt denied or ask reject
      Perm-->>Model: denied
    else approved
      Tools->>Sandbox: optional confinement
      Sandbox->>Host: execute
      Host-->>Model: tool result
    end
  end
```

Order (authoritative user-guide): (1) PreToolUse hooks (2) deny/ask/allow rules (3) remembered grants (4) built-in auto-approvals (5) mode policy. `bypassPermissions` short-circuits after step 2 with denials/hooks still applying.

## Used by

- [codegen tools + workspace](../systems/codegen.md)
- Interactive TUI approval UI; headless `dontAsk` CI

## Blast radius

Weakening deny-wins or skipping hooks can allow destructive commands. Mode changes affect CI safety defaults.

## See also

- [codegen](../systems/codegen.md)
- user-guide/10-hooks.md, 18-sandbox.md
