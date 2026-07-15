---
type: Module
title: "xai-tty-utils — Workspace crate"
description: >
  Open when changing the `xai-tty-utils` crate at `crates/codegen/xai-tty-utils`.
resource: "crates/codegen/xai-tty-utils"
tags: [crate, crates-codegen, rust]
timestamp: "2026-07-15T23:15:13Z"
x-grounded-paths: ["crates/codegen/xai-tty-utils/src/lib.rs", "crates/codegen/xai-tty-utils/Cargo.toml", "README.md"]
x-hotspot-score: 0.4
x-callers: ["systems/codegen.md"]
---

# xai-tty-utils — Workspace crate

## What it is

`xai-tty-utils` is a Cargo workspace member at `crates/codegen/xai-tty-utils` (2 `.rs` files).

Lightweight process-spawning utilities for TTY safety.  When a TUI/pager/raw-mode terminal owns the parent process's controlling TTY, every child process must be detached — otherwise it (or its grandchildren: npm, git, pinentry, ssh-agent …) can open `/dev/tty` directly and spew mouse escape codes, capability-probe replies, or credential prompts onto the live screen.  This crate provides the minim

**Role:** Workspace crate. [Graph: approximate via crate tree; Human:Synthesis from lib.rs docs]

## How it works

Primary surface is `src/lib.rs`.

Notable workspace dependencies (from crate Cargo.toml, truncated): `tokio`.

```mermaid
flowchart TB
  C["xai-tty-utils"]
  C --> Leaf["leaf / few internal deps"]
```

## Used by

- Parent cluster: [codegen](codegen.md)
- Other crates that depend on this package (see Cargo graph / `cargo tree -p xai-tty-utils`)

## Blast radius

Changes affect any consumer of `xai-tty-utils` in the workspace. Run `cargo test -p xai-tty-utils` and re-check dependent top crates (`xai-grok-shell`, `xai-grok-pager`, `xai-grok-tools`) when public APIs move.

## See also

- [systems/codegen.md](codegen.md)
- [entrypoint](../entrypoints/main.md)
- Workspace root `Cargo.toml` (generated — do not hand-edit)

## Notes

- Prefer `cargo check -p xai-tty-utils` / `cargo test -p xai-tty-utils` for this crate.
- Full workspace builds are slow; target the crate under change.
- See root README for build prerequisites (Rust toolchain, protoc).
