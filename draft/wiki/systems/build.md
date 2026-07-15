---
type: Module
title: "build — proto build helpers"
description: >
  Open when fixing protoc discovery, protobuf codegen build scripts, or hermetic builds that depend on bin/protoc.
resource: "crates/build/xai-proto-build"
tags: [build, protoc, protobuf]
timestamp: "2026-07-15T23:06:40Z"
x-grounded-paths: ["crates/build/xai-proto-build/src/lib.rs", "crates/build/xai-proto-build/src/find_protoc.rs", "bin/protoc", "crates/codegen/xai-grok-tools-api/build.rs", "README.md"]
x-hotspot-score: 0.5
x-callers: ["systems/codegen.md"]
---

# build — proto build helpers

## What it is


`crates/build/xai-proto-build` locates `protoc` (dotslash launcher at `bin/protoc`, `$PROTOC`, or PATH) for crates that generate Rust from `.proto` (notably `xai-grok-tools-api`). [Graph:High — package `build`]

Provenance: graph package inventory + repository layout synthesis. Agents should open grounded paths rather than treat this page as complete implementation documentation.

## How it works

```mermaid
flowchart LR
  BuildRs[crate build.rs] --> Find[xai-proto-build::find_protoc]
  Find --> Dotslash[bin/protoc]
  Find --> Env["$PROTOC / PATH"]
  Find --> Prost[prost-build / pbjson-build]
```

## Used by

- [codegen](codegen.md) crates with protobuf codegen (e.g. tools-api)

## Blast radius

Broken protoc resolution fails compile of proto-dependent crates. Prefer the checked-in `bin/protoc` for hermeticity.

## See also

- [codegen](codegen.md)
- README § Building from source

## Notes

- Supporting detail 1: keep graph package labels distinct from Cargo crate names when routing edits.
- Supporting detail 2: keep graph package labels distinct from Cargo crate names when routing edits.
- Supporting detail 3: keep graph package labels distinct from Cargo crate names when routing edits.
- Supporting detail 4: keep graph package labels distinct from Cargo crate names when routing edits.
- Supporting detail 5: keep graph package labels distinct from Cargo crate names when routing edits.
