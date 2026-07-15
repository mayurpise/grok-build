# grok-build — Draft Context

Start here. This indexes the Draft context for this repo.

## Start here
- **[Getting Started](getting-started.md)** — install, build from source, first launch, cargo loop
- Wiki mirrors: [overview/getting-started](wiki/overview/getting-started.md) · [features/getting-started](wiki/features/getting-started.md) · [wiki/getting-started.md](wiki/getting-started.md)

## Context
- [Architecture](architecture.md) — rendered linear view of wiki/ (OKF mode)
- [Product](product.md) — what this system does and for whom
- [Tech Stack](tech-stack.md) — languages, frameworks, infra
- [Workflow](workflow.md) — how work flows through the repo
- [Guardrails](guardrails.md) — learned conventions and anti-patterns
- [AI Context Map](.ai-context.md) — condensed orientation for agents (OKF index root)
- [AI Profile](.ai-profile.md) — repo profile + tiering

## Wiki (source of truth)
- [Wiki root / Concept Map](wiki/index.md)
- [Systems (all crates)](wiki/systems/index.md) — 79 workspace crates + parent maps
- [Features (user guide)](wiki/features/index.md) — product capabilities
- [Reference](wiki/reference/index.md) — config, protocol, deps, runbook
- [Entrypoint](wiki/entrypoints/main.md) — `xai-grok-pager` / `grok` binary
- [Overview](wiki/overview/index.md)

### Hot crates (shortcuts)
- [xai-grok-pager](wiki/systems/xai-grok-pager.md) — TUI
- [xai-grok-shell](wiki/systems/xai-grok-shell.md) — agent runtime
- [xai-grok-tools](wiki/systems/xai-grok-tools.md) — tools
- [xai-grok-workspace](wiki/systems/xai-grok-workspace.md) — FS/permissions
- [xai-grok-sampler](wiki/systems/xai-grok-sampler.md) — model streaming
- [codegen map](wiki/systems/codegen.md) · [common map](wiki/systems/common.md)

## Tracks
- [Track Index](tracks.md)

## Knowledge graph
- Engine-only (`codebase-memory-mcp`). Gate marker: `draft/graph/schema.yaml`.
