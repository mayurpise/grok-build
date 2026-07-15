---
type: Module
title: "dict — graph label → see xai-grok-config"
description: >
  Graph package label `dict` is low-fidelity. Prefer the real crate page `xai-grok-config`. Map-like settings live in config types — not a package boundary.
resource: "crates/codegen/xai-grok-config"
tags: [graph-noise, redirect]
timestamp: "2026-07-15T23:15:13Z"
x-grounded-paths: ["crates/codegen/xai-grok-config/src/lib.rs", "README.md"]
x-hotspot-score: 0.4
x-callers: ["systems/codegen.md"]
---

# dict — graph label → see xai-grok-config

## What it is

**This is not a Cargo crate.** The knowledge-graph engine clustered a low-node package labeled `dict`.

Map-like settings live in config types — not a package boundary.

**Canonical page:** [xai-grok-config.md](xai-grok-config.md)

## How it works

Do not implement features under a `dict` module path. Route work to `xai-grok-config` and related crates in the [codegen catalog](codegen.md).

```mermaid
flowchart TB
  Noise["graph label: dict"] --> Real["xai-grok-config"]
  Real --> Codegen[codegen catalog]
```

## Used by

- Agents misrouted by graph package list
- [codegen.md](codegen.md) parent map

## Blast radius

Mis-editing as if `dict` were a module wastes time. Always open `xai-grok-config` sources instead.

## See also

- [xai-grok-config.md](xai-grok-config.md)
- [codegen.md](codegen.md)

## Notes

- Prefer `cargo check -p dict` / `cargo test -p dict` for this crate.
- Full workspace builds are slow; target the crate under change.
- See root README for build prerequisites (Rust toolchain, protoc).
