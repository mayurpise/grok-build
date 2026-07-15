---
type: Module
title: "xai-grok-tools — Tool implementations"
description: >
  Open when adding/changing tools (file, shell, search, web, skills, MCP use_tool).
resource: "crates/codegen/xai-grok-tools"
tags: [crate, crates-codegen, rust]
timestamp: "2026-07-15T23:15:13Z"
x-grounded-paths: ["crates/codegen/xai-grok-tools/src/lib.rs", "crates/codegen/xai-grok-tools/Cargo.toml", "README.md"]
x-hotspot-score: 0.4
x-callers: ["systems/codegen.md"]
---

# xai-grok-tools — Tool implementations

## What it is

`xai-grok-tools` is a Cargo workspace member at `crates/codegen/xai-grok-tools` (211 `.rs` files).

Grok tools library.

**Role:** Tool implementations. [Graph: approximate via crate tree; Human:Synthesis from lib.rs docs]

## How it works

Primary surface is `src/lib.rs`.

Notable workspace dependencies (from crate Cargo.toml, truncated): `anyhow`, `arc-swap`, `dirs`, `derive_more`, `dunce`, `fs2`, `educe`, `async-openai`.

```mermaid
flowchart TB
  C["xai-grok-tools"]
  D0["xai-tty-utils"]
  C --> D0
  D1["xai-grok-config"]
  C --> D1
  D2["xai-grok-tools-api"]
  C --> D2
  D3["xai-grok-workspace-types"]
  C --> D3
```

## Used by

- Parent cluster: [codegen](codegen.md)
- Other crates that depend on this package (see Cargo graph / `cargo tree -p xai-grok-tools`)

## Blast radius

Changes affect any consumer of `xai-grok-tools` in the workspace. Run `cargo test -p xai-grok-tools` and re-check dependent top crates (`xai-grok-shell`, `xai-grok-pager`, `xai-grok-tools`) when public APIs move.

## See also

- [systems/codegen.md](codegen.md)
- [entrypoint](../entrypoints/main.md)
- Workspace root `Cargo.toml` (generated — do not hand-edit)
