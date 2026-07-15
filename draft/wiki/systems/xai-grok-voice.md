---
type: Module
title: "xai-grok-voice — Voice input"
description: >
  Open when changing voice capture/integration.
resource: "crates/codegen/xai-grok-voice"
tags: [crate, crates-codegen, rust]
timestamp: "2026-07-15T23:15:13Z"
x-grounded-paths: ["crates/codegen/xai-grok-voice/src/lib.rs", "crates/codegen/xai-grok-voice/Cargo.toml", "README.md"]
x-hotspot-score: 0.4
x-callers: ["systems/codegen.md"]
---

# xai-grok-voice — Voice input

## What it is

`xai-grok-voice` is a Cargo workspace member at `crates/codegen/xai-grok-voice` (15 `.rs` files).

Voice input for Grok Build CLI: an xAI streaming STT client and the `run_voice_pipeline` task that emits `VoiceEvent`s for the pager.  Voice is dictation only: mic → streaming STT → transcript into the prompt box.

**Role:** Voice input. [Graph: approximate via crate tree; Human:Synthesis from lib.rs docs]

## How it works

Primary surface is `src/lib.rs`.

Notable workspace dependencies (from crate Cargo.toml, truncated): `anyhow`, `futures-util`, `rustls`, `serde`, `serde_json`, `thiserror`, `tokio`, `tokio-tungstenite`.

```mermaid
flowchart TB
  C["xai-grok-voice"]
  C --> Leaf["leaf / few internal deps"]
```

## Used by

- Parent cluster: [codegen](codegen.md)
- Other crates that depend on this package (see Cargo graph / `cargo tree -p xai-grok-voice`)

## Blast radius

Changes affect any consumer of `xai-grok-voice` in the workspace. Run `cargo test -p xai-grok-voice` and re-check dependent top crates (`xai-grok-shell`, `xai-grok-pager`, `xai-grok-tools`) when public APIs move.

## See also

- [systems/codegen.md](codegen.md)
- [entrypoint](../entrypoints/main.md)
- Workspace root `Cargo.toml` (generated — do not hand-edit)

## Notes

- Prefer `cargo check -p xai-grok-voice` / `cargo test -p xai-grok-voice` for this crate.
- Full workspace builds are slow; target the crate under change.
- See root README for build prerequisites (Rust toolchain, protoc).
