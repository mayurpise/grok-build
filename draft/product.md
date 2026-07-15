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

# Product: Grok Build

| Field | Value |
|-------|-------|
| **Branch** | `main` → `origin/main` |
| **Commit** | `b189869` — Publish harness and TUI open-source |
| **Generated** | 2026-07-15T23:08:34Z |
| **Synced To** | `b189869b7755d2b482969acf6c92da3ecfeffd36` |

---

## Vision

Grok Build (`grok`) is SpaceXAI's terminal-based AI coding agent. It helps developers understand codebases, edit files, run shell commands, search the web, and manage long-running agent work — interactively in a full-screen TUI, headlessly for scripting/CI, or embedded in editors via the Agent Client Protocol (ACP).

## Target Users

### Primary Users
- **Software engineers**: Daily coding assistance in the terminal with codebase awareness, tools, and permissions.
- **CI / automation authors**: Headless single-prompt and scripted agent runs (`grok -p`, dontAsk mode).
- **IDE extension developers / power users**: ACP stdio/serve/relay integration.

### Secondary Users
- **Platform / security reviewers**: Permission rules, sandbox, hooks, audit of tool execution.
- **Internal SpaceXAI operators**: Distribution, auto-update, telemetry (as shipped).

## Core Features

### Must Have (P0)
1. **Interactive TUI agent** — scrollback chat, prompt, slash commands, model turns.
2. **Tool execution with permissions** — file/edit/shell/search under deny/ask/allow + modes + hooks.
3. **Auth to xAI backend** — browser/OIDC-style first-run and token refresh.
4. **Headless / scripted mode** — non-interactive prompts for automation.
5. **Session continuity** — resume, compaction, leader process reconnection.

### Should Have (P1)
1. **ACP IDE embedding** — stdio, serve, relay.
2. **MCP servers & skills/plugins/hooks** — extensibility surface.
3. **Sandboxing** — OS-level confinement for risky tools.
4. **Worktrees / VCS awareness** — multi-worktree agent isolation helpers.
5. **Markdown + Mermaid rendering** in scrollback.

### Nice to Have (P2)
1. Voice input, dashboard views, foreign session import (Claude/Codex).
2. Plugin marketplace flows.

## Success Criteria

- [ ] Users complete auth and first useful coding turn without docs diving.
- [ ] Destructive tool calls are gated by permission pipeline (deny wins).
- [ ] Headless CI mode fails closed under `dontAsk` without allow rules.
- [ ] ACP clients can complete a prompt+tool turn over stdio.
- [ ] Per-crate `cargo test` / `cargo check` remain the default developer loop.

## Constraints

### Technical
- Rust workspace, edition 2024, toolchain 1.92.0; macOS/Linux primary hosts.
- Root `Cargo.toml` is generated — edit per-crate manifests.
- External contributions not accepted (CONTRIBUTING.md).
- Model backend and proxy contracts must stay version-compatible (`cli-chat-proxy-types`).

### Business
- Apache-2.0 first-party license; third_party / ports retain original licenses.
- Public tree is source transparency + local builds, not an open contribution project.

### Timeline
- Ongoing internal development with periodic OSS sync.

## Non-Goals

- Accepting external PRs or building a general multi-vendor agent marketplace in this tree.
- Replacing the internal monorepo as the sole source of truth for all SpaceXAI services.
- Supporting every desktop OS equally (Windows best-effort).
- Implementing the full cloud chat-proxy service inside this repository.
