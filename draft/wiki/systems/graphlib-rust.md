---
type: Module
title: "graphlib_rust — Graphlib"
description: >
  Open when changing graph primitives for Mermaid.
resource: "third_party/graphlib_rust"
tags: [crate, third_party, rust]
timestamp: "2026-07-15T23:15:13Z"
x-grounded-paths: ["third_party/graphlib_rust/src/lib.rs", "third_party/graphlib_rust/Cargo.toml", "README.md"]
x-hotspot-score: 0.4
x-callers: ["systems/mermaid-to-svg.md"]
---

# graphlib_rust — Graphlib

## What it is

`graphlib_rust` is a Cargo workspace member at `third_party/graphlib_rust` (6 `.rs` files).

Rust crate `graphlib_rust` at `third_party/graphlib_rust`.

**Role:** Graphlib. [Graph: approximate via crate tree; Human:Synthesis from lib.rs docs]

## How it works

Primary surface is `src/lib.rs`.

Notable workspace dependencies (from crate Cargo.toml, truncated): `ordered_hashmap`.

```mermaid
flowchart TB
  C["graphlib_rust"]
  C --> Leaf["leaf / few internal deps"]
```

## Used by

- Parent cluster: [mermaid-to-svg](mermaid-to-svg.md)
- Other crates that depend on this package (see Cargo graph / `cargo tree -p graphlib_rust`)

## Blast radius

Changes affect any consumer of `graphlib_rust` in the workspace. Run `cargo test -p graphlib_rust` and re-check dependent top crates (`xai-grok-shell`, `xai-grok-pager`, `xai-grok-tools`) when public APIs move.

## See also

- [systems/mermaid-to-svg.md](mermaid-to-svg.md)
- [entrypoint](../entrypoints/main.md)
- Workspace root `Cargo.toml` (generated — do not hand-edit)

## Notes

- Prefer `cargo check -p graphlib_rust` / `cargo test -p graphlib_rust` for this crate.
- Full workspace builds are slow; target the crate under change.
- See root README for build prerequisites (Rust toolchain, protoc).
