---
type: Module
title: "int — graph label → see xai-token-estimation"
description: >
  Graph package label `int` is low-fidelity. Prefer the real crate page `xai-token-estimation`. Numeric helpers are scattered; token estimation is one real crate.
resource: "crates/codegen/xai-token-estimation"
tags: [graph-noise, redirect]
timestamp: "2026-07-15T23:15:13Z"
x-grounded-paths: ["crates/codegen/xai-token-estimation/src/lib.rs", "README.md"]
x-hotspot-score: 0.4
x-callers: ["systems/codegen.md"]
---

# int — graph label → see xai-token-estimation

## What it is

**This is not a Cargo crate.** The knowledge-graph engine clustered a low-node package labeled `int`.

Numeric helpers are scattered; token estimation is one real crate.

**Canonical page:** [xai-token-estimation.md](xai-token-estimation.md)

## How it works

Do not implement features under a `int` module path. Route work to `xai-token-estimation` and related crates in the [codegen catalog](codegen.md).

```mermaid
flowchart TB
  Noise["graph label: int"] --> Real["xai-token-estimation"]
  Real --> Codegen[codegen catalog]
```

## Used by

- Agents misrouted by graph package list
- [codegen.md](codegen.md) parent map

## Blast radius

Mis-editing as if `int` were a module wastes time. Always open `xai-token-estimation` sources instead.

## See also

- [xai-token-estimation.md](xai-token-estimation.md)
- [codegen.md](codegen.md)

## Notes

- Prefer `cargo check -p int` / `cargo test -p int` for this crate.
- Full workspace builds are slow; target the crate under change.
- See root README for build prerequisites (Rust toolchain, protoc).
