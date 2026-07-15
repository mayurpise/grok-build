---
type: Module
title: "xai-acp-lib — ACP protocol lib"
description: >
  Open when changing ACP gateway, channels, or message framing.
resource: "crates/codegen/xai-acp-lib"
tags: [crate, crates-codegen, rust]
timestamp: "2026-07-15T23:15:13Z"
x-grounded-paths: ["crates/codegen/xai-acp-lib/src/lib.rs", "crates/codegen/xai-acp-lib/Cargo.toml", "README.md"]
x-hotspot-score: 0.4
x-callers: ["systems/codegen.md"]
---

# xai-acp-lib — ACP protocol lib

## What it is

`xai-acp-lib` is a Cargo workspace member at `crates/codegen/xai-acp-lib` (8 `.rs` files).

Rust crate `xai-acp-lib` at `crates/codegen/xai-acp-lib`.

**Role:** ACP protocol lib. [Graph: approximate via crate tree; Human:Synthesis from lib.rs docs]

## How it works

Primary surface is `src/lib.rs`.

Notable workspace dependencies (from crate Cargo.toml, truncated): `agent-client-protocol`, `async-trait`, `derive_more`, `futures`, `serde.workspace`, `tokio`, `tracing`, `serde_json.workspace`.

```mermaid
flowchart TB
  C["xai-acp-lib"]
  C --> Leaf["leaf / few internal deps"]
```

## Used by

- Parent cluster: [codegen](codegen.md)
- Other crates that depend on this package (see Cargo graph / `cargo tree -p xai-acp-lib`)

## Blast radius

Changes affect any consumer of `xai-acp-lib` in the workspace. Run `cargo test -p xai-acp-lib` and re-check dependent top crates (`xai-grok-shell`, `xai-grok-pager`, `xai-grok-tools`) when public APIs move.

## See also

- [systems/codegen.md](codegen.md)
- [entrypoint](../entrypoints/main.md)
- Workspace root `Cargo.toml` (generated — do not hand-edit)

## Notes

- Prefer `cargo check -p xai-acp-lib` / `cargo test -p xai-acp-lib` for this crate.
- Full workspace builds are slow; target the crate under change.
- See root README for build prerequisites (Rust toolchain, protoc).
