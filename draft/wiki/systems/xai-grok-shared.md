---
type: Module
title: "xai-grok-shared — Shared CLI helpers"
description: >
  Open when changing cross-cutting shared utilities.
resource: "crates/codegen/xai-grok-shared"
tags: [crate, crates-codegen, rust]
timestamp: "2026-07-15T23:15:13Z"
x-grounded-paths: ["crates/codegen/xai-grok-shared/src/lib.rs", "crates/codegen/xai-grok-shared/Cargo.toml", "README.md"]
x-hotspot-score: 0.4
x-callers: ["systems/codegen.md"]
---

# xai-grok-shared — Shared CLI helpers

## What it is

`xai-grok-shared` is a Cargo workspace member at `crates/codegen/xai-grok-shared` (8 `.rs` files).

Shared utilities used by both `xai-grok-shell` and its downstream clients (e.g. `xai-grok-pager-render`). This crate sits upstream of `xai-grok-shell` so it must never depend on it.

**Role:** Shared CLI helpers. [Graph: approximate via crate tree; Human:Synthesis from lib.rs docs]

## How it works

Primary surface is `src/lib.rs`.

Notable workspace dependencies (from crate Cargo.toml, truncated): `agent-client-protocol`, `anyhow`, `base64`, `dirs`, `dunce`, `image`, `parking_lot`, `prod-mc-cli-chat-proxy-types`.

```mermaid
flowchart TB
  C["xai-grok-shared"]
  C --> Leaf["leaf / few internal deps"]
```

## Used by

- Parent cluster: [codegen](codegen.md)
- Other crates that depend on this package (see Cargo graph / `cargo tree -p xai-grok-shared`)

## Blast radius

Changes affect any consumer of `xai-grok-shared` in the workspace. Run `cargo test -p xai-grok-shared` and re-check dependent top crates (`xai-grok-shell`, `xai-grok-pager`, `xai-grok-tools`) when public APIs move.

## See also

- [systems/codegen.md](codegen.md)
- [entrypoint](../entrypoints/main.md)
- Workspace root `Cargo.toml` (generated — do not hand-edit)

## Notes

- Prefer `cargo check -p xai-grok-shared` / `cargo test -p xai-grok-shared` for this crate.
- Full workspace builds are slow; target the crate under change.
- See root README for build prerequisites (Rust toolchain, protoc).
