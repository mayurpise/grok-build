---
type: Module
title: "xai-grok-tools-api — Tools protobuf API"
description: >
  Open when changing tools wire proto or generated API shapes.
resource: "crates/codegen/xai-grok-tools-api"
tags: [crate, crates-codegen, rust]
timestamp: "2026-07-15T23:15:13Z"
x-grounded-paths: ["crates/codegen/xai-grok-tools-api/src/lib.rs", "crates/codegen/xai-grok-tools-api/Cargo.toml", "README.md"]
x-hotspot-score: 0.4
x-callers: ["systems/codegen.md"]
---

# xai-grok-tools-api — Tools protobuf API

## What it is

`xai-grok-tools-api` is a Cargo workspace member at `crates/codegen/xai-grok-tools-api` (5 `.rs` files).

Shared API definitions for Grok tools: protobuf types, config validation, and canonical slash-command wording.  Used by both the tools library and the gRPC server, and by host services that must not depend on the tools implementation crate.

**Role:** Tools protobuf API. [Graph: approximate via crate tree; Human:Synthesis from lib.rs docs]

## How it works

Primary surface is `src/lib.rs`.

Notable workspace dependencies (from crate Cargo.toml, truncated): `tonic-prost`, `prost`, `tonic`, `serde`, `serde_json`, `xai-tool-protocol`.

```mermaid
flowchart TB
  C["xai-grok-tools-api"]
  D0["xai-tool-protocol"]
  C --> D0
```

## Used by

- Parent cluster: [codegen](codegen.md)
- Other crates that depend on this package (see Cargo graph / `cargo tree -p xai-grok-tools-api`)

## Blast radius

Changes affect any consumer of `xai-grok-tools-api` in the workspace. Run `cargo test -p xai-grok-tools-api` and re-check dependent top crates (`xai-grok-shell`, `xai-grok-pager`, `xai-grok-tools`) when public APIs move.

## See also

- [systems/codegen.md](codegen.md)
- [entrypoint](../entrypoints/main.md)
- Workspace root `Cargo.toml` (generated — do not hand-edit)

## Notes

- Prefer `cargo check -p xai-grok-tools-api` / `cargo test -p xai-grok-tools-api` for this crate.
- Full workspace builds are slow; target the crate under change.
- See root README for build prerequisites (Rust toolchain, protoc).
