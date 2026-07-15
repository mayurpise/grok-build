---
type: Module
title: "dagre_rust — Dagre layout"
description: >
  Open when fixing graph layout in Mermaid stack.
resource: "third_party/dagre_rust"
tags: [crate, third_party, rust]
timestamp: "2026-07-15T23:15:13Z"
x-grounded-paths: ["third_party/dagre_rust/src/lib.rs", "third_party/dagre_rust/Cargo.toml", "README.md"]
x-hotspot-score: 0.4
x-callers: ["systems/mermaid-to-svg.md"]
---

# dagre_rust — Dagre layout

## What it is

`dagre_rust` is a Cargo workspace member at `third_party/dagre_rust` (24 `.rs` files).

Rust crate `dagre_rust` at `third_party/dagre_rust`.

**Role:** Dagre layout. [Graph: approximate via crate tree; Human:Synthesis from lib.rs docs]

## How it works

Primary surface is `src/lib.rs`.

Notable workspace dependencies (from crate Cargo.toml, truncated): `graphlib_rust`, `ordered_hashmap`.

```mermaid
flowchart TB
  C["dagre_rust"]
  C --> Leaf["leaf / few internal deps"]
```

## Used by

- Parent cluster: [mermaid-to-svg](mermaid-to-svg.md)
- Other crates that depend on this package (see Cargo graph / `cargo tree -p dagre_rust`)

## Blast radius

Changes affect any consumer of `dagre_rust` in the workspace. Run `cargo test -p dagre_rust` and re-check dependent top crates (`xai-grok-shell`, `xai-grok-pager`, `xai-grok-tools`) when public APIs move.

## See also

- [systems/mermaid-to-svg.md](mermaid-to-svg.md)
- [entrypoint](../entrypoints/main.md)
- Workspace root `Cargo.toml` (generated — do not hand-edit)

## Notes

- Prefer `cargo check -p dagre_rust` / `cargo test -p dagre_rust` for this crate.
- Full workspace builds are slow; target the crate under change.
- See root README for build prerequisites (Rust toolchain, protoc).
