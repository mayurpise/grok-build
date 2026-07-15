---
type: API
title: "Tool protocol API"
description: >
  Open when changing tool wire envelopes, registration, or tool runtime dispatch contracts.
resource: "crates/common/xai-tool-protocol"
tags: [reference]
timestamp: "2026-07-15T23:15:13Z"
x-grounded-paths: ["crates/common/xai-tool-protocol/src/lib.rs", "crates/common/xai-tool-runtime/src/lib.rs", "README.md"]
x-callers: []
---

# Tool protocol API

## What it is

Tool execution uses protocol types (`xai-tool-protocol`) and runtime dispatch (`xai-tool-runtime`) consumed by `xai-grok-tools`.

Implementation lives at `crates/common/xai-tool-protocol`.

## How it works

```mermaid
flowchart LR
  Model --> Tools[xai-grok-tools]
  Tools --> RT[xai-tool-runtime]
  RT --> Proto[xai-tool-protocol]
```

## See also

- [systems/xai-grok-config.md](../systems/xai-grok-config.md)
- [systems/xai-grok-tools.md](../systems/xai-grok-tools.md)
- [overview/architecture.md](../overview/architecture.md)
- User guide under crates/codegen/xai-grok-pager/docs/user-guide/
