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

# Guardrails

| Field | Value |
|-------|-------|
| **Branch** | `main` → `origin/main` |
| **Commit** | `b189869` |
| **Generated** | 2026-07-15T23:08:34Z |
| **Synced To** | `b189869b7755d2b482969acf6c92da3ecfeffd36` |

---

This file defines project-level guardrails and learned coding patterns.

## Hard Guardrails

### Git & Version Control
- [ ] No direct commits to main/master  <!-- internal process may land on main; OSS sync is special -->
- [x] No force push to shared branches without explicit coordination
- [ ] PR required for all changes  <!-- external PRs not accepted -->

### Code Quality
- [x] No secrets/credentials in code
- [x] Prefer `cargo check/test -p <crate>` over full workspace builds
- [x] Do not edit generated root `Cargo.toml` — edit per-crate manifests

### Security
- [x] No secrets/credentials in code
- [x] Permission **deny wins**; never weaken PreToolUse/hook deny paths without review
- [x] Treat Mermaid/SVG path as untrusted model input (vendored stack)
- [x] Sandbox + permission mode changes require safety review

### Testing
- [x] Non-trivial behavior changes need tests in the owning crate
- [x] No skipped tests without documented reason

### C++/Systems
- [ ] G1–G6 C++ guardrails — **not applicable** (Rust project)

### Rust-specific
- [x] Respect edition 2024 and workspace lints
- [x] Avoid unbounded blocking on the async runtime in session/leader paths
- [x] Preserve ACP/proxy wire compatibility when changing shared types

## Learned Conventions

| ID | Pattern | Evidence |
|----|---------|----------|
| LC-001 | Crate naming `xai-grok-*` / `xai-*` under `crates/codegen` and `crates/common` | Cargo workspace members |
| LC-002 | Composition root is `xai-grok-pager-bin`; library logic in pager/shell/tools/workspace | README + main.rs |
| LC-003 | User-facing docs live in `xai-grok-pager/docs/user-guide/` | docs tree |
| LC-004 | Third-party diagram stack vendored under `third_party/` with NOTICE | third_party/README.md |
| LC-005 | Tests often colocated `tests/` or `*_tests` modules; heavy suite on pager | tree scan |
| LC-006 | Feature flags and `workspace.dependencies` centralize versions | root Cargo.toml |
| LC-007 | Agent modes: TUI / headless / stdio ACP / leader | shell agent/app.rs |

## Learned Anti-Patterns

| ID | Pattern | Why bad | Evidence |
|----|---------|---------|----------|
| AP-001 | Full-workspace `cargo build` for every change | Extremely slow on this monorepo | README Development section |
| AP-002 | Editing root workspace Cargo.toml by hand | File is generated | README IMPORTANT note |
| AP-003 | Treating graph package labels (`str`,`list`,`dict`,`int`) as real crates | Graph noise; misroutes agents | draft graph packages |
| AP-004 | Bypassing permission pipeline in tools for convenience | Safety regression | user-guide/22 |
| AP-005 | Accepting external contributions / opening public PR workflow | Project policy | CONTRIBUTING.md |
