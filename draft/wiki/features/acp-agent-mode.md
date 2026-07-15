---
type: Feature
title: "ACP agent mode & IDE integration"
description: >
  Open when changing ACP stdio/serve/relay, gateway messages, IDE session lifecycle, or agent-client-protocol wiring.
resource: "crates/codegen/xai-acp-lib"
tags: [feature, acp, ide]
timestamp: "2026-07-15T23:06:40Z"
x-grounded-paths: ["crates/codegen/xai-acp-lib/src/gateway.rs", "crates/codegen/xai-grok-shell/src/agent/app.rs", "crates/codegen/xai-grok-pager/docs/user-guide/15-agent-mode.md", "README.md"]
x-hotspot-score: 0.5
x-callers: ["entrypoints/main.md", "systems/codegen.md"]
---

# ACP agent mode & IDE integration

## What it is


Agent Client Protocol integration: persistent agent process for IDEs via stdio JSON-RPC, optional WebSocket serve, and relay for remote access. [Existing:user-guide/15]

Provenance: graph package inventory + repository layout synthesis. Agents should open grounded paths rather than treat this page as complete implementation documentation.

## How it works

```mermaid
sequenceDiagram
  participant IDE
  participant Stdio as grok agent stdio
  participant Gateway as xai-acp-lib gateway
  participant Session as shell session
  IDE->>Stdio: JSON-RPC over stdin
  Stdio->>Gateway: frame parse
  Gateway->>Session: prompt / tool visibility
  Session-->>IDE: streamed results / thought
```

Commands: `grok agent stdio`, `grok agent serve --bind …`, relay mode for internet reachability.

## Used by

- IDE extensions (Zed, Neovim, Emacs, custom)
- [entrypoint](../entrypoints/main.md) agent subcommands

## Blast radius

Wire format breakage disconnects all IDE clients. Session resume semantics must stay compatible across reconnects.

## See also

- [codegen](../systems/codegen.md)
- [entrypoint](../entrypoints/main.md)

## Notes

- Supporting detail 1: keep graph package labels distinct from Cargo crate names when routing edits.
- Supporting detail 2: keep graph package labels distinct from Cargo crate names when routing edits.
- Supporting detail 3: keep graph package labels distinct from Cargo crate names when routing edits.
