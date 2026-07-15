---
type: Module
title: "xai-grok-announcements — Workspace crate"
description: >
  Open when changing the `xai-grok-announcements` crate at `crates/codegen/xai-grok-announcements`.
resource: "crates/codegen/xai-grok-announcements"
tags: [crate, crates-codegen, rust]
timestamp: "2026-07-15T23:15:13Z"
x-grounded-paths: ["crates/codegen/xai-grok-announcements/src/lib.rs", "crates/codegen/xai-grok-announcements/Cargo.toml", "README.md"]
x-hotspot-score: 0.4
x-callers: ["systems/codegen.md"]
---

# xai-grok-announcements — Workspace crate

## What it is

`xai-grok-announcements` is a Cargo workspace member at `crates/codegen/xai-grok-announcements` (1 `.rs` files).

Shared announcement types, persistence, and formatting for Grok CLI apps.  This crate provides the common logic used by `xai-grok-shell` and `xai-grok-pager` for handling announcements (banner notifications).

**Role:** Workspace crate. [Graph: approximate via crate tree; Human:Synthesis from lib.rs docs]

## How it works

Primary surface is `src/lib.rs`.

Notable workspace dependencies (from crate Cargo.toml, truncated): `chrono`, `serde`, `serde_json`, `tokio`, `tracing`, `ts-rs`, `xai-grok-tools`.

```mermaid
flowchart TB
  C["xai-grok-announcements"]
  D0["xai-grok-tools"]
  C --> D0
```

## Used by

- Parent cluster: [codegen](codegen.md)
- Other crates that depend on this package (see Cargo graph / `cargo tree -p xai-grok-announcements`)

## Blast radius

Changes affect any consumer of `xai-grok-announcements` in the workspace. Run `cargo test -p xai-grok-announcements` and re-check dependent top crates (`xai-grok-shell`, `xai-grok-pager`, `xai-grok-tools`) when public APIs move.

## See also

- [systems/codegen.md](codegen.md)
- [entrypoint](../entrypoints/main.md)
- Workspace root `Cargo.toml` (generated — do not hand-edit)

## Notes

- Prefer `cargo check -p xai-grok-announcements` / `cargo test -p xai-grok-announcements` for this crate.
- Full workspace builds are slow; target the crate under change.
- See root README for build prerequisites (Rust toolchain, protoc).
