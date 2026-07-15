---
type: Module
title: "ptyctl-cli — PTY control CLI"
description: >
  Open when changing ptyctl command-line.
resource: "crates/codegen/ptyctl-cli"
tags: [crate, crates-codegen, rust]
timestamp: "2026-07-15T23:15:13Z"
x-grounded-paths: ["crates/codegen/ptyctl-cli/src/main.rs", "crates/codegen/ptyctl-cli/Cargo.toml", "README.md"]
x-hotspot-score: 0.4
x-callers: ["systems/codegen.md"]
---

# ptyctl-cli — PTY control CLI

## What it is

`ptyctl-cli` is a Cargo workspace member at `crates/codegen/ptyctl-cli` (6 `.rs` files).

Rust crate `ptyctl-cli` at `crates/codegen/ptyctl-cli`.

**Role:** PTY control CLI. [Graph: approximate via crate tree; Human:Synthesis from lib.rs docs]

## How it works

Primary surface is `src/lib.rs` and `src/main.rs`.

Notable workspace dependencies (from crate Cargo.toml, truncated): `ptyctl`, `axum`, `clap`, `reqwest`, `tokio`, `serde`, `serde_json`, `anyhow`.

```mermaid
flowchart TB
  C["ptyctl-cli"]
  D0["ptyctl"]
  C --> D0
```

## Used by

- Parent cluster: [codegen](codegen.md)
- Other crates that depend on this package (see Cargo graph / `cargo tree -p ptyctl-cli`)

## Blast radius

Changes affect any consumer of `ptyctl-cli` in the workspace. Run `cargo test -p ptyctl-cli` and re-check dependent top crates (`xai-grok-shell`, `xai-grok-pager`, `xai-grok-tools`) when public APIs move.

## See also

- [systems/codegen.md](codegen.md)
- [entrypoint](../entrypoints/main.md)
- Workspace root `Cargo.toml` (generated — do not hand-edit)

## Notes

- Prefer `cargo check -p ptyctl-cli` / `cargo test -p ptyctl-cli` for this crate.
- Full workspace builds are slow; target the crate under change.
- See root README for build prerequisites (Rust toolchain, protoc).
