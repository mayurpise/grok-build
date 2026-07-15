---
type: Module
title: "ordered_hashmap — Ordered map"
description: >
  Open when fixing order-sensitive maps in Mermaid stack.
resource: "third_party/ordered_hashmap"
tags: [crate, third_party, rust]
timestamp: "2026-07-15T23:15:13Z"
x-grounded-paths: ["third_party/ordered_hashmap/src/lib.rs", "third_party/ordered_hashmap/Cargo.toml", "README.md"]
x-hotspot-score: 0.4
x-callers: ["systems/mermaid-to-svg.md"]
---

# ordered_hashmap — Ordered map

## What it is

`ordered_hashmap` is a Cargo workspace member at `third_party/ordered_hashmap` (1 `.rs` files).

Rust crate `ordered_hashmap` at `third_party/ordered_hashmap`.

**Role:** Ordered map. [Graph: approximate via crate tree; Human:Synthesis from lib.rs docs]

## How it works

Primary surface is `src/lib.rs`.

Notable workspace dependencies (from crate Cargo.toml, truncated): (few/none listed).

```mermaid
flowchart TB
  C["ordered_hashmap"]
  C --> Leaf["leaf / few internal deps"]
```

## Used by

- Parent cluster: [mermaid-to-svg](mermaid-to-svg.md)
- Other crates that depend on this package (see Cargo graph / `cargo tree -p ordered_hashmap`)

## Blast radius

Changes affect any consumer of `ordered_hashmap` in the workspace. Run `cargo test -p ordered_hashmap` and re-check dependent top crates (`xai-grok-shell`, `xai-grok-pager`, `xai-grok-tools`) when public APIs move.

## See also

- [systems/mermaid-to-svg.md](mermaid-to-svg.md)
- [entrypoint](../entrypoints/main.md)
- Workspace root `Cargo.toml` (generated — do not hand-edit)

## Notes

- Prefer `cargo check -p ordered_hashmap` / `cargo test -p ordered_hashmap` for this crate.
- Full workspace builds are slow; target the crate under change.
- See root README for build prerequisites (Rust toolchain, protoc).
