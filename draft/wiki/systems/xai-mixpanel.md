---
type: Module
title: "xai-mixpanel — Workspace crate"
description: >
  Open when changing the `xai-mixpanel` crate at `crates/codegen/xai-mixpanel`.
resource: "crates/codegen/xai-mixpanel"
tags: [crate, crates-codegen, rust]
timestamp: "2026-07-15T23:15:13Z"
x-grounded-paths: ["crates/codegen/xai-mixpanel/src/lib.rs", "crates/codegen/xai-mixpanel/Cargo.toml", "README.md"]
x-hotspot-score: 0.4
x-callers: ["systems/codegen.md"]
---

# xai-mixpanel — Workspace crate

## What it is

`xai-mixpanel` is a Cargo workspace member at `crates/codegen/xai-mixpanel` (1 `.rs` files).

Lightweight Mixpanel HTTP tracking client.  This is a minimal replacement for `mixpanel-rs` that uses `reqwest 0.12` instead of `reqwest 0.11`, avoiding a duplicate HTTP stack in the binary.  Only the `track` API is implemented since that's all we use.

**Role:** Workspace crate. [Graph: approximate via crate tree; Human:Synthesis from lib.rs docs]

## How it works

Primary surface is `src/lib.rs`.

Notable workspace dependencies (from crate Cargo.toml, truncated): `reqwest`, `serde_json`, `base64`, `thiserror`, `xai-grok-secrets`.

```mermaid
flowchart TB
  C["xai-mixpanel"]
  D0["xai-grok-secrets"]
  C --> D0
```

## Used by

- Parent cluster: [codegen](codegen.md)
- Other crates that depend on this package (see Cargo graph / `cargo tree -p xai-mixpanel`)

## Blast radius

Changes affect any consumer of `xai-mixpanel` in the workspace. Run `cargo test -p xai-mixpanel` and re-check dependent top crates (`xai-grok-shell`, `xai-grok-pager`, `xai-grok-tools`) when public APIs move.

## See also

- [systems/codegen.md](codegen.md)
- [entrypoint](../entrypoints/main.md)
- Workspace root `Cargo.toml` (generated — do not hand-edit)

## Notes

- Prefer `cargo check -p xai-mixpanel` / `cargo test -p xai-mixpanel` for this crate.
- Full workspace builds are slow; target the crate under change.
- See root README for build prerequisites (Rust toolchain, protoc).
