---
type: Module
title: "xai-hooks-plugins-types — Workspace crate"
description: >
  Open when changing the `xai-hooks-plugins-types` crate at `crates/codegen/xai-hooks-plugins-types`.
resource: "crates/codegen/xai-hooks-plugins-types"
tags: [crate, crates-codegen, rust]
timestamp: "2026-07-15T23:15:13Z"
x-grounded-paths: ["crates/codegen/xai-hooks-plugins-types/src/lib.rs", "crates/codegen/xai-hooks-plugins-types/Cargo.toml", "README.md"]
x-hotspot-score: 0.4
x-callers: ["systems/codegen.md"]
---

# xai-hooks-plugins-types — Workspace crate

## What it is

`xai-hooks-plugins-types` is a Cargo workspace member at `crates/codegen/xai-hooks-plugins-types` (1 `.rs` files).

Shared DTO types for hooks/plugins ACP extensions.  This crate defines the wire format for `x.ai/hooks/*` and `x.ai/plugins/*` ACP extension methods. It is dependency-free (only `serde`) so both `xai-grok-shell` and `xai-grok-pager` can depend on it without pulling in domain logic.  Conversion from domain types (`HookSpec`, `LoadedPlugin`) to these DTOs lives in the shell's extension handlers, not

**Role:** Workspace crate. [Graph: approximate via crate tree; Human:Synthesis from lib.rs docs]

## How it works

Primary surface is `src/lib.rs`.

Notable workspace dependencies (from crate Cargo.toml, truncated): `serde`.

```mermaid
flowchart TB
  C["xai-hooks-plugins-types"]
  C --> Leaf["leaf / few internal deps"]
```

## Used by

- Parent cluster: [codegen](codegen.md)
- Other crates that depend on this package (see Cargo graph / `cargo tree -p xai-hooks-plugins-types`)

## Blast radius

Changes affect any consumer of `xai-hooks-plugins-types` in the workspace. Run `cargo test -p xai-hooks-plugins-types` and re-check dependent top crates (`xai-grok-shell`, `xai-grok-pager`, `xai-grok-tools`) when public APIs move.

## See also

- [systems/codegen.md](codegen.md)
- [entrypoint](../entrypoints/main.md)
- Workspace root `Cargo.toml` (generated — do not hand-edit)

## Notes

- Prefer `cargo check -p xai-hooks-plugins-types` / `cargo test -p xai-hooks-plugins-types` for this crate.
- Full workspace builds are slow; target the crate under change.
- See root README for build prerequisites (Rust toolchain, protoc).
