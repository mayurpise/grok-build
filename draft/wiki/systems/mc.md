---
type: Module
title: "mc — cli-chat-proxy shared types"
description: >
  Open when changing wire types shared with the cli-chat-proxy backend: session metadata, sandbox flags, feedback, subagent bundles, deployment config.
resource: "prod/mc/cli-chat-proxy-types"
tags: [mc, proxy, types, api]
timestamp: "2026-07-15T23:06:40Z"
x-grounded-paths: ["prod/mc/cli-chat-proxy-types/src/lib.rs", "prod/mc/cli-chat-proxy-types/src/session_types.rs", "prod/mc/cli-chat-proxy-types/src/sandbox_types.rs", "README.md"]
x-hotspot-score: 0.5
x-callers: ["systems/codegen.md"]
---

# mc — cli-chat-proxy shared types

## What it is


`prod/mc/cli-chat-proxy-types` defines **shared serialization types** for the CLI ↔ chat-proxy boundary (session, storage, feedback, sandbox, deployment config, client metrics, subagent bundles). [Graph:High — package `mc`]

Provenance: graph package inventory + repository layout synthesis. Agents should open grounded paths rather than treat this page as complete implementation documentation.

## How it works

Pure types crate (serde-facing). Codegen shell/agent code imports these to speak the proxy's contract without embedding server code in the OSS tree.

```mermaid
flowchart LR
  CLI[xai-grok-shell / sampler] -->|JSON| Types[cli-chat-proxy-types]
  Types -.->|contract| Proxy[cli-chat-proxy service outside repo]
```

## Used by

- [codegen](codegen.md) agent/session/upload paths that talk to xAI backends

## Blast radius

Field renames or enum changes break CLI↔proxy compatibility across version skew. Coordinate with proxy deploy when evolving types.

## See also

- [codegen](codegen.md)
- [common](common.md)

## Notes

- Supporting detail 1: keep graph package labels distinct from Cargo crate names when routing edits.
- Supporting detail 2: keep graph package labels distinct from Cargo crate names when routing edits.
- Supporting detail 3: keep graph package labels distinct from Cargo crate names when routing edits.
- Supporting detail 4: keep graph package labels distinct from Cargo crate names when routing edits.
- Supporting detail 5: keep graph package labels distinct from Cargo crate names when routing edits.
