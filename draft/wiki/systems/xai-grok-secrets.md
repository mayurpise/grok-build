---
type: Module
title: "xai-grok-secrets — Secret sanitizer"
description: >
  Open when changing secret redaction.
resource: "crates/codegen/xai-grok-secrets"
tags: [crate, crates-codegen, rust]
timestamp: "2026-07-15T23:15:13Z"
x-grounded-paths: ["crates/codegen/xai-grok-secrets/src/lib.rs", "crates/codegen/xai-grok-secrets/Cargo.toml", "README.md"]
x-hotspot-score: 0.4
x-callers: ["systems/codegen.md"]
---

# xai-grok-secrets — Secret sanitizer

## What it is

`xai-grok-secrets` is a Cargo workspace member at `crates/codegen/xai-grok-secrets` (2 `.rs` files).

Rust crate `xai-grok-secrets` at `crates/codegen/xai-grok-secrets`.

**Role:** Secret sanitizer. [Graph: approximate via crate tree; Human:Synthesis from lib.rs docs]

## How it works

Primary surface is `src/lib.rs`.

Notable workspace dependencies (from crate Cargo.toml, truncated): `regex`, `serde_json`, `url`.

```mermaid
flowchart TB
  C["xai-grok-secrets"]
  C --> Leaf["leaf / few internal deps"]
```

## Used by

- Parent cluster: [codegen](codegen.md)
- Other crates that depend on this package (see Cargo graph / `cargo tree -p xai-grok-secrets`)

## Blast radius

Changes affect any consumer of `xai-grok-secrets` in the workspace. Run `cargo test -p xai-grok-secrets` and re-check dependent top crates (`xai-grok-shell`, `xai-grok-pager`, `xai-grok-tools`) when public APIs move.

## See also

- [systems/codegen.md](codegen.md)
- [entrypoint](../entrypoints/main.md)
- Workspace root `Cargo.toml` (generated — do not hand-edit)

## Notes

- Prefer `cargo check -p xai-grok-secrets` / `cargo test -p xai-grok-secrets` for this crate.
- Full workspace builds are slow; target the crate under change.
- See root README for build prerequisites (Rust toolchain, protoc).
