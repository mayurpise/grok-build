---
type: DataModel
title: "Glossary"
description: >
  Open for definitions of pager, shell, leader, ACP, sampler, workspace,
  permission mode, hooks, MCP, and related Grok Build terms.
resource: crates/codegen/xai-grok-pager/docs/user-guide
tags: [glossary]
timestamp: "2026-07-15T23:06:40Z"
x-grounded-paths: ["README.md", "crates/codegen/xai-grok-pager/docs/user-guide/README.md"]
x-hotspot-score: 0.1
x-callers: []
---

# Glossary

## What it is


Shared vocabulary for the Grok Build monorepo.

Provenance: graph package inventory + repository layout synthesis. Agents should open grounded paths rather than treat this page as complete implementation documentation.

## How it works

| Term | Meaning |
|------|---------|
| **pager** | Full-screen TUI (`xai-grok-pager`) |
| **shell** | Agent runtime crate (`xai-grok-shell`) — sessions, leader, headless |
| **leader** | Long-lived agent process clients reconnect to |
| **ACP** | Agent Client Protocol — IDE embedding (stdio/serve/relay) |
| **sampler** | Model streaming client (`xai-grok-sampler`) |
| **workspace** | Host FS/VCS/permission crate (`xai-grok-workspace`) |
| **permission mode** | default / dontAsk / bypassPermissions / acceptEdits / plan |
| **hooks** | User scripts on tool lifecycle (PreToolUse, etc.) |
| **MCP** | Model Context Protocol servers for extra tools |
| **compaction** | Summarizing old transcript to free context |
| **skills** | Packaged agent skill markdown + scripts |
| **sandbox** | OS-level confinement for tool/shell execution |

## See also

- [architecture](architecture.md)
- User guide index
