---
type: Module
title: "xai-ratatui-textarea — Workspace crate"
description: >
  Open when changing the `xai-ratatui-textarea` crate at `crates/codegen/xai-ratatui-textarea`.
resource: "crates/codegen/xai-ratatui-textarea"
tags: [crate, crates-codegen, rust]
timestamp: "2026-07-15T23:15:13Z"
x-grounded-paths: ["crates/codegen/xai-ratatui-textarea/src/lib.rs", "crates/codegen/xai-ratatui-textarea/Cargo.toml", "README.md"]
x-hotspot-score: 0.4
x-callers: ["systems/codegen.md"]
---

# xai-ratatui-textarea — Workspace crate

## What it is

`xai-ratatui-textarea` is a Cargo workspace member at `crates/codegen/xai-ratatui-textarea` (6 `.rs` files).

Rust crate `xai-ratatui-textarea` at `crates/codegen/xai-ratatui-textarea`.

**Role:** Workspace crate. [Graph: approximate via crate tree; Human:Synthesis from lib.rs docs]

## How it works

Primary surface is `src/lib.rs`.

Notable workspace dependencies (from crate Cargo.toml, truncated): `crossterm`, `ratatui`, `ratatui-core`, `textwrap`, `tracing`, `tui-scrollbar`, `unicode-segmentation`, `unicode-width`.

```mermaid
flowchart TB
  C["xai-ratatui-textarea"]
  C --> Leaf["leaf / few internal deps"]
```

## Used by

- Parent cluster: [codegen](codegen.md)
- Other crates that depend on this package (see Cargo graph / `cargo tree -p xai-ratatui-textarea`)

## Blast radius

Changes affect any consumer of `xai-ratatui-textarea` in the workspace. Run `cargo test -p xai-ratatui-textarea` and re-check dependent top crates (`xai-grok-shell`, `xai-grok-pager`, `xai-grok-tools`) when public APIs move.

## See also

- [systems/codegen.md](codegen.md)
- [entrypoint](../entrypoints/main.md)
- Workspace root `Cargo.toml` (generated — do not hand-edit)

## Notes

- Prefer `cargo check -p xai-ratatui-textarea` / `cargo test -p xai-ratatui-textarea` for this crate.
- Full workspace builds are slow; target the crate under change.
- See root README for build prerequisites (Rust toolchain, protoc).
