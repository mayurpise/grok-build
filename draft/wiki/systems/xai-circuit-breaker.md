---
type: Module
title: "xai-circuit-breaker — Circuit breaker"
description: >
  Open when changing open/half-open breaker policy.
resource: "crates/common/xai-circuit-breaker"
tags: [crate, crates-common, rust]
timestamp: "2026-07-15T23:15:13Z"
x-grounded-paths: ["crates/common/xai-circuit-breaker/src/lib.rs", "crates/common/xai-circuit-breaker/Cargo.toml", "README.md"]
x-hotspot-score: 0.4
x-callers: ["systems/common.md"]
---

# xai-circuit-breaker — Circuit breaker

## What it is

`xai-circuit-breaker` is a Cargo workspace member at `crates/common/xai-circuit-breaker` (18 `.rs` files).

Shared HTTP circuit breaker.  Sliding-window-with-min-samples algorithm: the breaker trips when `sample_count >= min_samples AND error_rate >= error_rate_threshold` over the live window. Server- and client-side consumers run the same state machine and pick a preset via `BreakerConfig::server` or `BreakerConfig::client`.

**Role:** Circuit breaker. [Graph: approximate via crate tree; Human:Synthesis from lib.rs docs]

## How it works

Primary surface is `src/lib.rs`.

Notable workspace dependencies (from crate Cargo.toml, truncated): `log`.

```mermaid
flowchart TB
  C["xai-circuit-breaker"]
  C --> Leaf["leaf / few internal deps"]
```

## Used by

- Parent cluster: [common](common.md)
- Other crates that depend on this package (see Cargo graph / `cargo tree -p xai-circuit-breaker`)

## Blast radius

Changes affect any consumer of `xai-circuit-breaker` in the workspace. Run `cargo test -p xai-circuit-breaker` and re-check dependent top crates (`xai-grok-shell`, `xai-grok-pager`, `xai-grok-tools`) when public APIs move.

## See also

- [systems/common.md](common.md)
- [entrypoint](../entrypoints/main.md)
- Workspace root `Cargo.toml` (generated — do not hand-edit)

## Notes

- Prefer `cargo check -p xai-circuit-breaker` / `cargo test -p xai-circuit-breaker` for this crate.
- Full workspace builds are slow; target the crate under change.
- See root README for build prerequisites (Rust toolchain, protoc).
