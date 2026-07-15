---
type: Module
title: "xai-grok-workspace-client — Workspace client"
description: >
  Open when changing workspace client adapters.
resource: "crates/codegen/xai-grok-workspace-client"
tags: [crate, crates-codegen, rust]
timestamp: "2026-07-15T23:15:13Z"
x-grounded-paths: ["crates/codegen/xai-grok-workspace-client/src/lib.rs", "crates/codegen/xai-grok-workspace-client/Cargo.toml", "README.md"]
x-hotspot-score: 0.4
x-callers: ["systems/codegen.md"]
---

# xai-grok-workspace-client — Workspace client

## What it is

`xai-grok-workspace-client` is a Cargo workspace member at `crates/codegen/xai-grok-workspace-client` (1 `.rs` files).

Typed client for hub-proxied `workspace.*` RPC methods — the single transport for the `workspace_rpc` channel, shared by `WorkspaceOps` proxy mode and by consumers that cannot depend on `xai-grok-workspace`. Wire types live in `xai_grok_workspace_types::rpc`; this crate adds the connected-state latch, the generic `WorkspaceClient::rpc` core, and error mapping.  No deadline is imposed by default 

**Role:** Workspace client. [Graph: approximate via crate tree; Human:Synthesis from lib.rs docs]

## How it works

Primary surface is `src/lib.rs`.

Notable workspace dependencies (from crate Cargo.toml, truncated): `serde`, `serde_json`, `thiserror`, `tokio`, `tracing`, `xai-computer-hub-sdk`, `xai-grok-workspace-types`, `xai-tool-protocol`.

```mermaid
flowchart TB
  C["xai-grok-workspace-client"]
  D0["xai-computer-hub-sdk"]
  C --> D0
  D1["xai-grok-workspace-types"]
  C --> D1
  D2["xai-tool-protocol"]
  C --> D2
  D3["xai-tool-runtime"]
  C --> D3
```

## Used by

- Parent cluster: [codegen](codegen.md)
- Other crates that depend on this package (see Cargo graph / `cargo tree -p xai-grok-workspace-client`)

## Blast radius

Changes affect any consumer of `xai-grok-workspace-client` in the workspace. Run `cargo test -p xai-grok-workspace-client` and re-check dependent top crates (`xai-grok-shell`, `xai-grok-pager`, `xai-grok-tools`) when public APIs move.

## See also

- [systems/codegen.md](codegen.md)
- [entrypoint](../entrypoints/main.md)
- Workspace root `Cargo.toml` (generated — do not hand-edit)
