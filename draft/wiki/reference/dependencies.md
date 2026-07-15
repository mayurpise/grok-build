---
type: Dependency
title: "Key external dependencies"
description: >
  Open when upgrading major deps (tokio, ratatui, reqwest, ACP, rmcp) or auditing supply chain.
resource: "Cargo.toml"
tags: [reference]
timestamp: "2026-07-15T23:15:13Z"
x-grounded-paths: ["Cargo.toml", "THIRD-PARTY-NOTICES", "README.md"]
x-callers: []
---

# Key external dependencies

## What it is

Major external deps: tokio, ratatui/crossterm, serde, reqwest 0.12 (MCP crate quarantines reqwest 0.13/rmcp), agent-client-protocol, gix, notify, prost/OTEL stack. Vendored Mermaid stack under third_party/.

## Used by

- Entire CLI closure via workspace.dependencies
- See crate Cargo.toml files for feature flags

- Prefer workspace.dependencies pins in the generated root Cargo.toml workflow.
- Vendored third_party licenses are tracked in third_party/NOTICE.
