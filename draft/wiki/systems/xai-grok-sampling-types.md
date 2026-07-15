---
type: Module
title: "xai-grok-sampling-types — Sampling shared types"
description: >
  Open when changing sampling event/type contracts.
resource: "crates/codegen/xai-grok-sampling-types"
tags: [crate, crates-codegen, rust]
timestamp: "2026-07-15T23:15:13Z"
x-grounded-paths: ["crates/codegen/xai-grok-sampling-types/src/lib.rs", "crates/codegen/xai-grok-sampling-types/Cargo.toml", "README.md"]
x-hotspot-score: 0.4
x-callers: ["systems/codegen.md"]
---

# xai-grok-sampling-types — Sampling shared types

## What it is

`xai-grok-sampling-types` is a Cargo workspace member at `crates/codegen/xai-grok-sampling-types` (7 `.rs` files).

Pure data types for the xAI sampling / chat-completion API layer.  This crate contains the API-agnostic conversation types, chat completion request/response types, streaming types, and error types used across the xAI agent stack.  It intentionally contains **no I/O** (no HTTP clients, no file system access) so it can be depended on by downstream crates (e.g., `xai-chat-state`) without pulling in t

**Role:** Sampling shared types. [Graph: approximate via crate tree; Human:Synthesis from lib.rs docs]

## How it works

Primary surface is `src/lib.rs`.

Notable workspace dependencies (from crate Cargo.toml, truncated): `async-openai`, `indexmap`, `reqwest`, `serde`, `serde_json`, `thiserror`, `tracing`, `xai-grok-compaction`.

```mermaid
flowchart TB
  C["xai-grok-sampling-types"]
  D0["xai-grok-compaction"]
  C --> D0
  D1["xai-grok-tools"]
  C --> D1
```

## Used by

- Parent cluster: [codegen](codegen.md)
- Other crates that depend on this package (see Cargo graph / `cargo tree -p xai-grok-sampling-types`)

## Blast radius

Changes affect any consumer of `xai-grok-sampling-types` in the workspace. Run `cargo test -p xai-grok-sampling-types` and re-check dependent top crates (`xai-grok-shell`, `xai-grok-pager`, `xai-grok-tools`) when public APIs move.

## See also

- [systems/codegen.md](codegen.md)
- [entrypoint](../entrypoints/main.md)
- Workspace root `Cargo.toml` (generated — do not hand-edit)
