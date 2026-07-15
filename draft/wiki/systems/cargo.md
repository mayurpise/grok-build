---
type: Module
title: "cargo — graph label → see xai-grok-pager-bin"
description: >
  Graph package label `cargo` is low-fidelity. Prefer the real crate page `xai-grok-pager-bin`. Cargo workspace root is generated; start from composition root crate.
resource: "crates/codegen/xai-grok-pager-bin"
tags: [graph-noise, redirect]
timestamp: "2026-07-15T23:15:13Z"
x-grounded-paths: ["README.md", "Cargo.toml"]
x-hotspot-score: 0.4
x-callers: ["systems/codegen.md"]
---

# cargo — graph label → see xai-grok-pager-bin

## What it is

**This is not a Cargo crate.** The knowledge-graph engine clustered a low-node package labeled `cargo`.

Cargo workspace root is generated; start from composition root crate.

**Canonical page:** [xai-grok-pager-bin.md](xai-grok-pager-bin.md)

## How it works

Do not implement features under a `cargo` module path. Route work to `xai-grok-pager-bin` and related crates in the [codegen catalog](codegen.md).

```mermaid
flowchart TB
  Noise["graph label: cargo"] --> Real["xai-grok-pager-bin"]
  Real --> Codegen[codegen catalog]
```

## Used by

- Agents misrouted by graph package list
- [codegen.md](codegen.md) parent map

## Blast radius

Mis-editing as if `cargo` were a module wastes time. Always open `xai-grok-pager-bin` sources instead.

## See also

- [xai-grok-pager-bin.md](xai-grok-pager-bin.md)
- [codegen.md](codegen.md)

## Notes

- Prefer `cargo check -p cargo` / `cargo test -p cargo` for this crate.
- Full workspace builds are slow; target the crate under change.
- See root README for build prerequisites (Rust toolchain, protoc).
