---
type: Module
title: "xai-grok-agent — Agent core helpers"
description: >
  Open when changing agent-side helpers used by shell/pager.
resource: "crates/codegen/xai-grok-agent"
tags: [crate, crates-codegen, rust]
timestamp: "2026-07-15T23:15:13Z"
x-grounded-paths: ["crates/codegen/xai-grok-agent/src/lib.rs", "crates/codegen/xai-grok-agent/Cargo.toml", "README.md"]
x-hotspot-score: 0.4
x-callers: ["systems/codegen.md"]
---

# xai-grok-agent — Agent core helpers

## What it is

`xai-grok-agent` is a Cargo workspace member at `crates/codegen/xai-grok-agent` (30 `.rs` files).

Agent builder, definition parsing, and system prompt assembly.  This crate extracts a first-class `Agent` type from `xai-grok-shell`. An `Agent` bundles tools, system prompt, system-reminder policy, compaction policy, and model configuration into a single, portable object that any host can consume.

**Role:** Agent core helpers. [Graph: approximate via crate tree; Human:Synthesis from lib.rs docs]

## How it works

Primary surface is `src/lib.rs`.

Notable workspace dependencies (from crate Cargo.toml, truncated): `dunce`, `xai-grok-hooks`, `xai-grok-sampling-types`, `xai-grok-tools`, `xai-token-estimation`, `minijinja`, `git2`, `regex`.

```mermaid
flowchart TB
  C["xai-grok-agent"]
  D0["xai-grok-hooks"]
  C --> D0
  D1["xai-grok-sampling-types"]
  C --> D1
  D2["xai-grok-tools"]
  C --> D2
  D3["xai-token-estimation"]
  C --> D3
```

## Used by

- Parent cluster: [codegen](codegen.md)
- Other crates that depend on this package (see Cargo graph / `cargo tree -p xai-grok-agent`)

## Blast radius

Changes affect any consumer of `xai-grok-agent` in the workspace. Run `cargo test -p xai-grok-agent` and re-check dependent top crates (`xai-grok-shell`, `xai-grok-pager`, `xai-grok-tools`) when public APIs move.

## See also

- [systems/codegen.md](codegen.md)
- [entrypoint](../entrypoints/main.md)
- Workspace root `Cargo.toml` (generated — do not hand-edit)
