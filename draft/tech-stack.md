---
project: "grok-build"
module: "root"
generated_by: "draft:init"
generated_at: "2026-07-15T23:08:34Z"
git:
  branch: "main"
  remote: "origin/main"
  commit: "b189869b7755d2b482969acf6c92da3ecfeffd36"
  commit_short: "b189869"
  commit_date: "2026-07-15 23:47:40 +0100"
  commit_message: "Publish harness and TUI open-source"
  dirty: false
synced_to_commit: "b189869b7755d2b482969acf6c92da3ecfeffd36"
---

# Tech Stack

| Field | Value |
|-------|-------|
| **Branch** | `main` → `origin/main` |
| **Commit** | `b189869` |
| **Generated** | 2026-07-15T23:08:34Z |
| **Synced To** | `b189869b7755d2b482969acf6c92da3ecfeffd36` |

---

## Languages

| Language | Version | Purpose |
|----------|---------|---------|
| Rust | 1.92.0 (`rust-toolchain.toml`) | Primary CLI/TUI/agent runtime |
| TOML | — | Cargo manifests, clippy/rustfmt config |
| Protobuf | via protoc / prost | `xai-grok-tools-api` wire shapes |
| Markdown | — | User guide, skills, prompts |
| Python / JS | minimal | helper scripts, npm packaging for pager |

## Frameworks & Libraries

### Core
| Name | Version (workspace) | Purpose |
|------|---------------------|---------|
| tokio | 1 (full) | Async runtime |
| ratatui + crossterm | 0.29 / 0.28 | TUI |
| serde / serde_json | 1 | Serialization |
| reqwest | 0.12 (rustls) | HTTP client |
| axum | 0.8 | Local HTTP/WS surfaces |
| agent-client-protocol | 0.10.4 | ACP IDE protocol |
| async-openai | 0.33 | OpenAI-compatible client features |
| prost / tonic-related OTEL | 0.14 / 0.32 | Proto + telemetry |
| gix | 0.83 | Git operations |
| notify | 8 | Filesystem watch |
| portable-pty / alacritty_terminal | — | PTY / terminal emulation |
| pulldown-cmark | 0.13 | Markdown |
| mermaid-to-svg (vendored) | path | Diagram SVG |
| parking_lot / dashmap / moka | — | Concurrency / cache |

### Development
| Name | Purpose |
|------|---------|
| rustfmt / clippy | Format + lint (repo configs) |
| criterion | Benchmarks |
| insta | Snapshot tests |
| mockito | HTTP mocks |

## Database

| Type | Technology | Purpose |
|------|------------|---------|
| Local | SQLite (via workspace crates) | Journals / local persistence where used |
| Remote | xAI chat proxy / API | Model + session backend (out of tree) |

## Testing

| Level | Framework | Coverage Target |
|-------|-----------|-----------------|
| Unit / integration | `cargo test -p <crate>` | Per-crate; large suite under pager/shell/tools |
| Snapshot | insta | UI/render regressions |
| Bench | criterion | Hot paths (markdown, pty, fsnotify) |
| E2E | crate integration tests + harness crates | Pager PTY harness |

## Build & Deploy

### Build
- **Tool**: Cargo workspace (resolver 2)
- **Binary**: `cargo build -p xai-grok-pager-bin --release` → `target/release/xai-grok-pager` (shipped as `grok`)
- **Proto**: `bin/protoc` (dotslash) + `xai-proto-build`

### CI/CD
- Internal SpaceXAI pipelines (not fully represented in this OSS snapshot)
- Developer validation: `cargo check/test/clippy -p <crate>`

### Deployment
- Install scripts: `https://x.ai/cli/install.sh` / PowerShell equivalent
- Auto-update via `xai-grok-update`

## Code Patterns

- Large modular workspace: many `xai-grok-*` crates with clear layering (bin → pager/shell → tools/workspace → common leaves).
- Async Tokio throughout agent/session/network paths; TUI event loop with effects.
- Permission pipeline is ordered and mode-sensitive (hooks → rules → grants → auto-approve → mode).
- Vendored third_party for untrusted diagram render path.
- Prefer per-crate builds; root Cargo.toml is generated/read-only.
