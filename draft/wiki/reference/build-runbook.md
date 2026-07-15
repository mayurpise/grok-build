---
type: Runbook
title: "Build and test runbook"
description: >
  Open for day-to-day build/test/clippy commands and protoc requirements.
resource: "README.md"
tags: [reference, runbook]
timestamp: "2026-07-15T23:15:13Z"
x-grounded-paths: ["README.md", "rust-toolchain.toml"]
x-callers: []
---

# Build and test runbook

```sh
cargo run -p xai-grok-pager-bin
cargo check -p <crate>
cargo test -p <crate>
cargo clippy -p <crate>
cargo fmt --all
```
Rust 1.92.0; protoc via bin/protoc.
