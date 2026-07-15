---
type: Module
title: "xai-grok-env — Workspace crate"
description: >
  Open when changing the `xai-grok-env` crate at `crates/codegen/xai-grok-env`.
resource: "crates/codegen/xai-grok-env"
tags: [crate, crates-codegen, rust]
timestamp: "2026-07-15T23:15:13Z"
x-grounded-paths: ["crates/codegen/xai-grok-env/src/lib.rs", "crates/codegen/xai-grok-env/Cargo.toml", "README.md"]
x-hotspot-score: 0.4
x-callers: ["systems/codegen.md"]
---

# xai-grok-env — Workspace crate

## What it is

`xai-grok-env` is a Cargo workspace member at `crates/codegen/xai-grok-env` (1 `.rs` files).

Backend environment presets for the Grok CLI crate family: endpoint URL defaults, environment selection, and env-var test support.  Public builds expose production endpoints. Values resolve as a `GROK_*` env-var override when set, else the compiled production default.

**Role:** Workspace crate. [Graph: approximate via crate tree; Human:Synthesis from lib.rs docs]

## How it works

Primary surface is `src/lib.rs`.

Notable workspace dependencies (from crate Cargo.toml, truncated): `tracing`, `url`.

```mermaid
flowchart TB
  C["xai-grok-env"]
  C --> Leaf["leaf / few internal deps"]
```

## Used by

- Parent cluster: [codegen](codegen.md)
- Other crates that depend on this package (see Cargo graph / `cargo tree -p xai-grok-env`)

## Blast radius

Changes affect any consumer of `xai-grok-env` in the workspace. Run `cargo test -p xai-grok-env` and re-check dependent top crates (`xai-grok-shell`, `xai-grok-pager`, `xai-grok-tools`) when public APIs move.

## See also

- [systems/codegen.md](codegen.md)
- [entrypoint](../entrypoints/main.md)
- Workspace root `Cargo.toml` (generated — do not hand-edit)

## Notes

- Prefer `cargo check -p xai-grok-env` / `cargo test -p xai-grok-env` for this crate.
- Full workspace builds are slow; target the crate under change.
- See root README for build prerequisites (Rust toolchain, protoc).
