---
type: Module
title: "xai-prompt-queue — Workspace crate"
description: >
  Open when changing the `xai-prompt-queue` crate at `crates/codegen/xai-prompt-queue`.
resource: "crates/codegen/xai-prompt-queue"
tags: [crate, crates-codegen, rust]
timestamp: "2026-07-15T23:15:13Z"
x-grounded-paths: ["crates/codegen/xai-prompt-queue/src/lib.rs", "crates/codegen/xai-prompt-queue/Cargo.toml", "README.md"]
x-hotspot-score: 0.4
x-callers: ["systems/codegen.md"]
---

# xai-prompt-queue — Workspace crate

## What it is

`xai-prompt-queue` is a Cargo workspace member at `crates/codegen/xai-prompt-queue` (2 `.rs` files).

Shared prompt-queue wire types for xai-grok-shell and xai-grok-pager.

**Role:** Workspace crate. [Graph: approximate via crate tree; Human:Synthesis from lib.rs docs]

## How it works

Primary surface is `src/lib.rs`.

Notable workspace dependencies (from crate Cargo.toml, truncated): `serde`.

```mermaid
flowchart TB
  C["xai-prompt-queue"]
  C --> Leaf["leaf / few internal deps"]
```

## Used by

- Parent cluster: [codegen](codegen.md)
- Other crates that depend on this package (see Cargo graph / `cargo tree -p xai-prompt-queue`)

## Blast radius

Changes affect any consumer of `xai-prompt-queue` in the workspace. Run `cargo test -p xai-prompt-queue` and re-check dependent top crates (`xai-grok-shell`, `xai-grok-pager`, `xai-grok-tools`) when public APIs move.

## See also

- [systems/codegen.md](codegen.md)
- [entrypoint](../entrypoints/main.md)
- Workspace root `Cargo.toml` (generated — do not hand-edit)

## Notes

- Prefer `cargo check -p xai-prompt-queue` / `cargo test -p xai-prompt-queue` for this crate.
- Full workspace builds are slow; target the crate under change.
- See root README for build prerequisites (Rust toolchain, protoc).
