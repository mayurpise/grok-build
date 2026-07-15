---
type: Module
title: "profile — graph label → see xai-grok-shell-base"
description: >
  Graph package label `profile` is low-fidelity. Prefer the real crate page `xai-grok-shell-base`. CPU profiling lives in shell-base; --agent-profile is CLI path resolution.
resource: "crates/codegen/xai-grok-shell-base"
tags: [graph-noise, redirect]
timestamp: "2026-07-15T23:15:13Z"
x-grounded-paths: ["crates/codegen/xai-grok-shell-base/src/lib.rs", "README.md"]
x-hotspot-score: 0.4
x-callers: ["systems/codegen.md"]
---

# profile — graph label → see xai-grok-shell-base

## What it is

**This is not a Cargo crate.** The knowledge-graph engine clustered a low-node package labeled `profile`.

CPU profiling lives in shell-base; --agent-profile is CLI path resolution.

**Canonical page:** [xai-grok-shell-base.md](xai-grok-shell-base.md)

## How it works

Do not implement features under a `profile` module path. Route work to `xai-grok-shell-base` and related crates in the [codegen catalog](codegen.md).

```mermaid
flowchart TB
  Noise["graph label: profile"] --> Real["xai-grok-shell-base"]
  Real --> Codegen[codegen catalog]
```

## Used by

- Agents misrouted by graph package list
- [codegen.md](codegen.md) parent map

## Blast radius

Mis-editing as if `profile` were a module wastes time. Always open `xai-grok-shell-base` sources instead.

## See also

- [xai-grok-shell-base.md](xai-grok-shell-base.md)
- [codegen.md](codegen.md)

## Notes

- Prefer `cargo check -p profile` / `cargo test -p profile` for this crate.
- Full workspace builds are slow; target the crate under change.
- See root README for build prerequisites (Rust toolchain, protoc).
