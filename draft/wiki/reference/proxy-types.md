---
type: DataModel
title: "cli-chat-proxy wire types"
description: >
  Open when changing session/sandbox/feedback types shared with the chat proxy backend.
resource: "prod/mc/cli-chat-proxy-types"
tags: [reference]
timestamp: "2026-07-15T23:15:13Z"
x-grounded-paths: ["prod/mc/cli-chat-proxy-types/src/lib.rs", "prod/mc/cli-chat-proxy-types/src/session_types.rs", "README.md"]
x-callers: []
---

# cli-chat-proxy wire types

## What it is

Serde types for CLI ↔ chat-proxy compatibility. Field renames require coordinated deploys.

Implementation lives at `prod/mc/cli-chat-proxy-types`.

## How it works

```mermaid
flowchart LR
  CLI --> Types[cli-chat-proxy-types] -.-> Proxy[chat-proxy service]
```

## See also

- [systems/xai-grok-config.md](../systems/xai-grok-config.md)
- [systems/xai-grok-tools.md](../systems/xai-grok-tools.md)
- [overview/architecture.md](../overview/architecture.md)
- User guide under crates/codegen/xai-grok-pager/docs/user-guide/
