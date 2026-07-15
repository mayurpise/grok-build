---
type: Module
title: "xai-tool-protocol — Tool wire protocol"
description: >
  Open when changing tool JSON-RPC envelopes or registration wire.
resource: "crates/common/xai-tool-protocol"
tags: [crate, crates-common, rust]
timestamp: "2026-07-15T23:15:13Z"
x-grounded-paths: ["crates/common/xai-tool-protocol/src/lib.rs", "crates/common/xai-tool-protocol/Cargo.toml", "README.md"]
x-hotspot-score: 0.4
x-callers: ["systems/common.md"]
---

# xai-tool-protocol — Tool wire protocol

## What it is

`xai-tool-protocol` is a Cargo workspace member at `crates/common/xai-tool-protocol` (21 `.rs` files).

xAI Computer Hub — wire-protocol types.  Identifier newtypes, registration payloads, capabilities, hook events, handshake messages, the JSON-RPC 2.0 envelope and method catalog, the `ToolErrorWire` / `ToolOutputWire` / `WireToolNotification` wire enums, every method's `params` / `result` payload struct, and the numeric ↔ string error-code mapping.

**Role:** Tool wire protocol. [Graph: approximate via crate tree; Human:Synthesis from lib.rs docs]

## How it works

Primary surface is `src/lib.rs`.

Notable workspace dependencies (from crate Cargo.toml, truncated): `xai-tool-types`, `serde`, `serde_json`, `thiserror`, `uuid`.

```mermaid
flowchart TB
  C["xai-tool-protocol"]
  D0["xai-tool-types"]
  C --> D0
```

## Used by

- Parent cluster: [common](common.md)
- Other crates that depend on this package (see Cargo graph / `cargo tree -p xai-tool-protocol`)

## Blast radius

Changes affect any consumer of `xai-tool-protocol` in the workspace. Run `cargo test -p xai-tool-protocol` and re-check dependent top crates (`xai-grok-shell`, `xai-grok-pager`, `xai-grok-tools`) when public APIs move.

## See also

- [systems/common.md](common.md)
- [entrypoint](../entrypoints/main.md)
- Workspace root `Cargo.toml` (generated — do not hand-edit)

## Notes

- Prefer `cargo check -p xai-tool-protocol` / `cargo test -p xai-tool-protocol` for this crate.
- Full workspace builds are slow; target the crate under change.
- See root README for build prerequisites (Rust toolchain, protoc).
