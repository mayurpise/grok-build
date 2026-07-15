---
type: Module
title: "xai-grok-version — Workspace crate"
description: >
  Open when changing the `xai-grok-version` crate at `crates/codegen/xai-grok-version`.
resource: "crates/codegen/xai-grok-version"
tags: [crate, crates-codegen, rust]
timestamp: "2026-07-15T23:15:13Z"
x-grounded-paths: ["crates/codegen/xai-grok-version/src/lib.rs", "crates/codegen/xai-grok-version/Cargo.toml", "README.md"]
x-hotspot-score: 0.4
x-callers: ["systems/codegen.md"]
---

# xai-grok-version — Workspace crate

## What it is

`xai-grok-version` is a Cargo workspace member at `crates/codegen/xai-grok-version` (2 `.rs` files).

Installed grok CLI version, lockstepped with shipping binaries.

**Role:** Workspace crate. [Graph: approximate via crate tree; Human:Synthesis from lib.rs docs]

## How it works

Primary surface is `src/lib.rs`.

Notable workspace dependencies (from crate Cargo.toml, truncated): `semver`.

```mermaid
flowchart TB
  C["xai-grok-version"]
  C --> Leaf["leaf / few internal deps"]
```

## Used by

- Parent cluster: [codegen](codegen.md)
- Other crates that depend on this package (see Cargo graph / `cargo tree -p xai-grok-version`)

## Blast radius

Changes affect any consumer of `xai-grok-version` in the workspace. Run `cargo test -p xai-grok-version` and re-check dependent top crates (`xai-grok-shell`, `xai-grok-pager`, `xai-grok-tools`) when public APIs move.

## See also

- [systems/codegen.md](codegen.md)
- [entrypoint](../entrypoints/main.md)
- Workspace root `Cargo.toml` (generated — do not hand-edit)

## Notes

- Prefer `cargo check -p xai-grok-version` / `cargo test -p xai-grok-version` for this crate.
- Full workspace builds are slow; target the crate under change.
- See root README for build prerequisites (Rust toolchain, protoc).
