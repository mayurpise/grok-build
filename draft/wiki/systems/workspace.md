---
type: Module
title: "workspace — graph label → see xai-grok-workspace"
description: >
  Graph package label `workspace` is low-fidelity. Prefer the real crate page `xai-grok-workspace`. Prefer the real `xai-grok-workspace` crate page.
resource: "crates/codegen/xai-grok-workspace"
tags: [graph-noise, redirect]
timestamp: "2026-07-15T23:15:13Z"
x-grounded-paths: ["crates/codegen/xai-grok-workspace/src/lib.rs", "README.md"]
x-hotspot-score: 0.4
x-callers: ["systems/codegen.md"]
---

# workspace — graph label → see xai-grok-workspace

## What it is

**This is not a Cargo crate.** The knowledge-graph engine clustered a low-node package labeled `workspace`.

Prefer the real `xai-grok-workspace` crate page.

**Canonical page:** [xai-grok-workspace.md](xai-grok-workspace.md)

## How it works

Do not implement features under a `workspace` module path. Route work to `xai-grok-workspace` and related crates in the [codegen catalog](codegen.md).

```mermaid
flowchart TB
  Noise["graph label: workspace"] --> Real["xai-grok-workspace"]
  Real --> Codegen[codegen catalog]
```

## Used by

- Agents misrouted by graph package list
- [codegen.md](codegen.md) parent map

## Blast radius

Mis-editing as if `workspace` were a module wastes time. Always open `xai-grok-workspace` sources instead.

## See also

- [xai-grok-workspace.md](xai-grok-workspace.md)
- [codegen.md](codegen.md)

## Notes

- Prefer `cargo check -p workspace` / `cargo test -p workspace` for this crate.
- Full workspace builds are slow; target the crate under change.
- See root README for build prerequisites (Rust toolchain, protoc).
