---
type: Subsystem
title: "grok-build — Wiki"
description: >
  Root index of the project wiki. Start here, then route into overview/, systems/,
  features/, reference/, or entrypoints/ via the Concept Map.
resource: .
tags: [index]
timestamp: "2026-07-15T23:06:40Z"
okf_version: "0.1"
okf_types_version: "0.1"
---

# grok-build — Wiki

> Project wiki. One concept per file; cross-links form the graph. The live call
> graph (`codebase-memory-mcp`) is the grounding source; this wiki is the
> navigable serialization. `../.ai-context.md` is the consumption entry point.

## Sections

| Section | Holds | Index |
|---------|-------|-------|
| `overview/` | System map, getting-started, glossary | [overview/index.md](overview/index.md) |
| `systems/` | Subsystems & modules (graph clusters) | [systems/index.md](systems/index.md) |
| `features/` | User-facing capabilities spanning modules | [features/index.md](features/index.md) |
| `reference/` | APIs, data models, dependencies, ADRs, runbooks | [reference/index.md](reference/index.md) |
| `entrypoints/` | Binaries / mains / CLIs | see pages below |

## Concept Map

<!-- CONCEPT-MAP:START -->
| Concept | Type | Open it when… |
|---------|------|---------------|
| [xai-grok-pager binary (grok CLI)](entrypoints/main.md) | Entrypoint | Open when changing CLI startup, mode dispatch (TUI/headless/agent/leader), auto-update, jemalloc, or composition-root wiring between pager and shell. |
| [ACP agent mode & IDE integration](features/acp-agent-mode.md) | Feature | Open when changing ACP stdio/serve/relay, gateway messages, IDE session lifecycle, or agent-client-protocol wiring. |
| [Agent mode (ACP) (product feature)](features/agent-mode-acp.md) | Feature | Open when changing ACP IDE integration modes. |
| [Authentication (product feature)](features/authentication.md) | Feature | Open when changing login, tokens, or reauth flows. |
| [Background tasks (product feature)](features/background-tasks.md) | Feature | Open when changing background command/subagent tasks. |
| [Configuration (product feature)](features/configuration.md) | Feature | Open when changing config.toml schema or merge layers. |
| [Custom models (product feature)](features/custom-models.md) | Feature | Open when changing model IDs or custom model config. |
| [Dashboard (product feature)](features/dashboard.md) | Feature | Open when changing in-TUI dashboard views. |
| [Getting started (product feature)](features/getting-started.md) | Feature | Open for install, first launch, and onboarding. |
| [Headless mode (product feature)](features/headless-mode.md) | Feature | Open when changing `grok -p` / non-interactive runs. |
| [Hooks (product feature)](features/hooks.md) | Feature | Open when changing hook events or hook scripts. |
| [Keyboard shortcuts (product feature)](features/keyboard-shortcuts.md) | Feature | Open when changing keybindings or input handling. |
| [MCP servers (product feature)](features/mcp-servers.md) | Feature | Open when changing MCP server config or lifecycle. |
| [Memory (product feature)](features/memory.md) | Feature | Open when changing cross-session memory features. |
| [Monitoring and usage (product feature)](features/monitoring-usage.md) | Feature | Open when changing usage metrics or monitoring UX. |
| [Permissions and safety (product feature)](features/permissions-and-safety.md) | Feature | Open when changing permission rules, modes, or dangerous-command policy. |
| [Plan mode (product feature)](features/plan-mode.md) | Feature | Open when changing plan-mode workflow. |
| [Plugins (product feature)](features/plugins.md) | Feature | Open when changing plugin load/install. |
| [Project rules (product feature)](features/project-rules.md) | Feature | Open when changing AGENTS.md/project rule loading. |
| [Sandbox (product feature)](features/sandbox.md) | Feature | Open when changing OS sandbox profiles. |
| [Sessions (product feature)](features/sessions.md) | Feature | Open when changing session list/resume/persistence. |
| [Skills (product feature)](features/skills.md) | Feature | Open when changing skill discovery or skill tools. |
| [Slash commands (product feature)](features/slash-commands.md) | Feature | Open when adding or changing /commands in the TUI. |
| [Subagents (product feature)](features/subagents.md) | Feature | Open when changing subagent spawn/lifecycle. |
| [Terminal support (product feature)](features/terminal-support.md) | Feature | Open when changing terminal capability detection. |
| [Theming (product feature)](features/theming.md) | Feature | Open when changing UI themes or color schemes. |
| [Tool authorization pipeline](features/tool-authorization.md) | Feature | Open when changing permission rules, modes, PreToolUse hooks, remembered grants, dangerous-command lists, or sandbox interaction with tool execution. |
| [Grok Build — system architecture overview](overview/architecture.md) | Subsystem | Open for a sparse whole-repo map of the Grok CLI monorepo: process roles, |
| [Getting started — build and run](overview/getting-started.md) | Runbook | Open for build prerequisites, cargo run/check commands, auth first-launch, and |
| [Glossary](overview/glossary.md) | DataModel | Open for definitions of pager, shell, leader, ACP, sampler, workspace, |
| [Build and test runbook](reference/build-runbook.md) | Runbook | Open for day-to-day build/test/clippy commands and protoc requirements. |
| [Configuration surface](reference/config.md) | API | Open when changing config files, env vars, managed config, or CLI flags that affect runtime. |
| [Key external dependencies](reference/dependencies.md) | Dependency | Open when upgrading major deps (tokio, ratatui, reqwest, ACP, rmcp) or auditing supply chain. |
| [cli-chat-proxy wire types](reference/proxy-types.md) | DataModel | Open when changing session/sandbox/feedback types shared with the chat proxy backend. |
| [Tool protocol API](reference/tool-protocol.md) | API | Open when changing tool wire envelopes, registration, or tool runtime dispatch contracts. |
| [build — proto build helpers](systems/build.md) | Module | Open when fixing protoc discovery, protobuf codegen build scripts, or hermetic builds that depend on bin/protoc. |
| [cargo — graph label → see xai-grok-pager-bin](systems/cargo.md) | Module | Graph package label `cargo` is low-fidelity. Prefer the real crate page `xai-grok-pager-bin`. Cargo workspace root is generated; start from composition root crate. |
| [cli-chat-proxy-types — Chat proxy types](systems/cli-chat-proxy-types.md) | Module | Open when changing CLI↔proxy serde contracts. |
| [codegen — primary CLI crate closure](systems/codegen.md) | Module | Open when changing the Grok CLI/TUI, agent runtime, tools, workspace, config, MCP, markdown, auth, or sampler. Parent of all crates/codegen/* pages. |
| [common — shared leaf crates](systems/common.md) | Module | Open when working on tool protocol/runtime, compaction, circuit breakers, computer-hub, or shared tracing under crates/common/. |
| [dagre_rust — Dagre layout](systems/dagre-rust.md) | Module | Open when fixing graph layout in Mermaid stack. |
| [dict — graph label → see xai-grok-config](systems/dict.md) | Module | Graph package label `dict` is low-fidelity. Prefer the real crate page `xai-grok-config`. Map-like settings live in config types — not a package boundary. |
| [graphlib_rust — Graphlib](systems/graphlib-rust.md) | Module | Open when changing graph primitives for Mermaid. |
| [int — graph label → see xai-token-estimation](systems/int.md) | Module | Graph package label `int` is low-fidelity. Prefer the real crate page `xai-token-estimation`. Numeric helpers are scattered; token estimation is one real crate. |
| [list — graph label → see xai-grok-shell](systems/list.md) | Module | Graph package label `list` is low-fidelity. Prefer the real crate page `xai-grok-shell`. List UIs live in pager/shell session listing — not a package boundary. |
| [mc — cli-chat-proxy shared types](systems/mc.md) | Module | Open when changing wire types shared with the cli-chat-proxy backend: session metadata, sandbox flags, feedback, subagent bundles, deployment config. |
| [mermaid-to-svg — Mermaid→SVG](systems/mermaid-to-svg.md) | Module | Open when fixing diagram SVG rendering (vendored). |
| [ordered_hashmap — Ordered map](systems/ordered-hashmap.md) | Module | Open when fixing order-sensitive maps in Mermaid stack. |
| [profile — graph label → see xai-grok-shell-base](systems/profile.md) | Module | Graph package label `profile` is low-fidelity. Prefer the real crate page `xai-grok-shell-base`. CPU profiling lives in shell-base; --agent-profile is CLI path resolution. |
| [ptyctl-cli — PTY control CLI](systems/ptyctl-cli.md) | Module | Open when changing ptyctl command-line. |
| [ptyctl — PTY control lib](systems/ptyctl.md) | Module | Open when changing PTY control primitives. |
| [str — graph label → see xai-grok-secrets](systems/str.md) | Module | Graph package label `str` is low-fidelity. Prefer the real crate page `xai-grok-secrets`. String/secret handling is not a package; see secrets sanitizer and string-heavy crates. |
| [workspace — graph label → see xai-grok-workspace](systems/workspace.md) | Module | Graph package label `workspace` is low-fidelity. Prefer the real crate page `xai-grok-workspace`. Prefer the real `xai-grok-workspace` crate page. |
| [xai-acp-lib — ACP protocol lib](systems/xai-acp-lib.md) | Module | Open when changing ACP gateway, channels, or message framing. |
| [xai-agent-lifecycle — Agent lifecycle](systems/xai-agent-lifecycle.md) | Module | Open when changing agent start/stop/lifecycle contributors. |
| [xai-chat-state — Chat state actor](systems/xai-chat-state.md) | Module | Open when changing conversation state, persistence, or compaction hooks. |
| [xai-circuit-breaker — Circuit breaker](systems/xai-circuit-breaker.md) | Module | Open when changing open/half-open breaker policy. |
| [xai-codebase-graph — Code index graph](systems/xai-codebase-graph.md) | Module | Open when changing tree-sitter index, goto-def/ref, or incremental reindex. |
| [xai-computer-hub-core — Computer hub core](systems/xai-computer-hub-core.md) | Module | Open when changing hub tool registry/transport core. |
| [xai-computer-hub-mcp-adapter — Hub MCP adapter](systems/xai-computer-hub-mcp-adapter.md) | Module | Open when bridging computer hub to MCP. |
| [xai-computer-hub-sdk — Computer hub SDK](systems/xai-computer-hub-sdk.md) | Module | Open when changing hub client connection/handshake. |
| [xai-crash-handler — Workspace crate](systems/xai-crash-handler.md) | Module | Open when changing the `xai-crash-handler` crate at `crates/codegen/xai-crash-handler`. |
| [xai-fast-worktree — Fast git worktrees](systems/xai-fast-worktree.md) | Module | Open when changing CoW/BTRFS worktree creation or pools. |
| [xai-file-utils — File utilities](systems/xai-file-utils.md) | Module | Open when changing shared file helpers. |
| [xai-fsnotify — FS notify](systems/xai-fsnotify.md) | Module | Open when changing filesystem watchers. |
| [xai-gix-status — Workspace crate](systems/xai-gix-status.md) | Module | Open when changing the `xai-gix-status` crate at `crates/codegen/xai-gix-status`. |
| [xai-grok-agent — Agent core helpers](systems/xai-grok-agent.md) | Module | Open when changing agent-side helpers used by shell/pager. |
| [xai-grok-announcements — Workspace crate](systems/xai-grok-announcements.md) | Module | Open when changing the `xai-grok-announcements` crate at `crates/codegen/xai-grok-announcements`. |
| [xai-grok-auth — Authentication](systems/xai-grok-auth.md) | Module | Open when changing OIDC/browser auth or token refresh. |
| [xai-grok-compaction — Context compaction](systems/xai-grok-compaction.md) | Module | Open when changing intra/inter/history/code compaction. |
| [xai-grok-config — Config loading/merge](systems/xai-grok-config.md) | Module | Open when changing config.toml layers, managed config, or version overrides. |
| [xai-grok-config-types — Config type defs](systems/xai-grok-config-types.md) | Module | Open when changing config schema types. |
| [xai-grok-env — Workspace crate](systems/xai-grok-env.md) | Module | Open when changing the `xai-grok-env` crate at `crates/codegen/xai-grok-env`. |
| [xai-grok-hooks — Hooks runtime](systems/xai-grok-hooks.md) | Module | Open when changing PreToolUse/session hooks discovery or execution. |
| [xai-grok-http — HTTP helpers](systems/xai-grok-http.md) | Module | Open when changing shared HTTP client wrappers. |
| [xai-grok-markdown-core — Workspace crate](systems/xai-grok-markdown-core.md) | Module | Open when changing the `xai-grok-markdown-core` crate at `crates/codegen/xai-grok-markdown-core`. |
| [xai-grok-markdown — Streaming markdown TUI](systems/xai-grok-markdown.md) | Module | Open when changing markdown/code/math/mermaid rendering in scrollback. |
| [xai-grok-mcp — MCP integration](systems/xai-grok-mcp.md) | Module | Open when changing MCP servers, OAuth, credentials, or rmcp quarantine. |
| [xai-grok-memory — Cross-session memory](systems/xai-grok-memory.md) | Module | Open when changing MEMORY.md storage, dream/search, or experimental memory. |
| [xai-grok-mermaid — Mermaid integration](systems/xai-grok-mermaid.md) | Module | Open when wiring Mermaid diagrams into markdown/TUI. |
| [xai-grok-models — Model catalog](systems/xai-grok-models.md) | Module | Open when changing default model lists. |
| [xai-grok-pager-bin — Entrypoint composition root](systems/xai-grok-pager-bin.md) | Module | Open when changing CLI binary startup, mode dispatch, jemalloc, or auto-update wiring. |
| [xai-grok-pager — Full-screen TUI](systems/xai-grok-pager.md) | Module | Open when changing TUI scrollback, prompt, slash commands, modals, event loop, or pager UI. |
| [xai-grok-pager-minimal — Minimal scrollback-native mode](systems/xai-grok-pager-minimal.md) | Module | Open when changing minimal pager mode seams or lightweight UI. |
| [xai-grok-pager-pty-harness — PTY harness / benches](systems/xai-grok-pager-pty-harness.md) | Module | Open when changing PTY integration tests or paste-latency benches. |
| [xai-grok-pager-render — Pager render engine](systems/xai-grok-pager-render.md) | Module | Open when changing terminal rendering, themes, or scrollback paint paths. |
| [xai-grok-paths — Workspace crate](systems/xai-grok-paths.md) | Module | Open when changing the `xai-grok-paths` crate at `crates/codegen/xai-grok-paths`. |
| [xai-grok-plugin-marketplace — Plugin marketplace](systems/xai-grok-plugin-marketplace.md) | Module | Open when changing plugin discovery/install marketplace. |
| [xai-grok-sampler — Model sampling/streaming](systems/xai-grok-sampler.md) | Module | Open when changing HTTP streaming, retry, sampler actor, or model backends. |
| [xai-grok-sampling-types — Sampling shared types](systems/xai-grok-sampling-types.md) | Module | Open when changing sampling event/type contracts. |
| [xai-grok-sandbox — OS sandbox](systems/xai-grok-sandbox.md) | Module | Open when changing Landlock/Seatbelt profiles or child network policy. |
| [xai-grok-secrets — Secret sanitizer](systems/xai-grok-secrets.md) | Module | Open when changing secret redaction. |
| [xai-grok-shared — Shared CLI helpers](systems/xai-grok-shared.md) | Module | Open when changing cross-cutting shared utilities. |
| [xai-grok-shell-base — Shell base helpers](systems/xai-grok-shell-base.md) | Module | Open when changing CPU profile, env helpers shared by shell. |
| [xai-grok-shell — Agent runtime](systems/xai-grok-shell.md) | Module | Open when changing sessions, leader, headless/stdio agent, relay, or shell-side tool orchestration. |
| [xai-grok-shell-session-support — Workspace crate](systems/xai-grok-shell-session-support.md) | Module | Open when changing the `xai-grok-shell-session-support` crate at `crates/codegen/xai-grok-shell-session-support`. |
| [xai-grok-subagent-resolution — Workspace crate](systems/xai-grok-subagent-resolution.md) | Module | Open when changing the `xai-grok-subagent-resolution` crate at `crates/codegen/xai-grok-subagent-resolution`. |
| [xai-grok-telemetry — Telemetry engine](systems/xai-grok-telemetry.md) | Module | Open when changing product events, OTEL, Sentry, or unified log. |
| [xai-grok-test-support — Workspace crate](systems/xai-grok-test-support.md) | Module | Open when changing the `xai-grok-test-support` crate at `crates/codegen/xai-grok-test-support`. |
| [xai-grok-tools-api — Tools protobuf API](systems/xai-grok-tools-api.md) | Module | Open when changing tools wire proto or generated API shapes. |
| [xai-grok-tools — Tool implementations](systems/xai-grok-tools.md) | Module | Open when adding/changing tools (file, shell, search, web, skills, MCP use_tool). |
| [xai-grok-update — Auto-update](systems/xai-grok-update.md) | Module | Open when changing binary update check/install. |
| [xai-grok-version — Workspace crate](systems/xai-grok-version.md) | Module | Open when changing the `xai-grok-version` crate at `crates/codegen/xai-grok-version`. |
| [xai-grok-voice — Voice input](systems/xai-grok-voice.md) | Module | Open when changing voice capture/integration. |
| [xai-grok-workspace-client — Workspace client](systems/xai-grok-workspace-client.md) | Module | Open when changing workspace client adapters. |
| [xai-grok-workspace — Host FS/VCS/permissions](systems/xai-grok-workspace.md) | Module | Open when changing filesystem, permission pipeline, worktrees, foreign sessions, or hub. |
| [xai-grok-workspace-types — Workspace request types](systems/xai-grok-workspace-types.md) | Module | Open when changing workspace RPC/request message types. |
| [xai-hooks-plugins-types — Workspace crate](systems/xai-hooks-plugins-types.md) | Module | Open when changing the `xai-hooks-plugins-types` crate at `crates/codegen/xai-hooks-plugins-types`. |
| [xai-hunk-tracker — Hunk tracker actor](systems/xai-hunk-tracker.md) | Module | Open when changing edit hunk tracking actors. |
| [xai-interjection-core — Workspace crate](systems/xai-interjection-core.md) | Module | Open when changing the `xai-interjection-core` crate at `crates/common/xai-interjection-core`. |
| [xai-mixpanel — Workspace crate](systems/xai-mixpanel.md) | Module | Open when changing the `xai-mixpanel` crate at `crates/codegen/xai-mixpanel`. |
| [xai-prompt-queue — Workspace crate](systems/xai-prompt-queue.md) | Module | Open when changing the `xai-prompt-queue` crate at `crates/codegen/xai-prompt-queue`. |
| [xai-proto-build — Protoc finder](systems/xai-proto-build.md) | Module | Open when fixing hermetic protoc discovery. |
| [xai-ratatui-inline — Workspace crate](systems/xai-ratatui-inline.md) | Module | Open when changing the `xai-ratatui-inline` crate at `crates/codegen/xai-ratatui-inline`. |
| [xai-ratatui-textarea — Workspace crate](systems/xai-ratatui-textarea.md) | Module | Open when changing the `xai-ratatui-textarea` crate at `crates/codegen/xai-ratatui-textarea`. |
| [xai-sqlite-journal — Workspace crate](systems/xai-sqlite-journal.md) | Module | Open when changing the `xai-sqlite-journal` crate at `crates/codegen/xai-sqlite-journal`. |
| [xai-system-power — Workspace crate](systems/xai-system-power.md) | Module | Open when changing the `xai-system-power` crate at `crates/codegen/xai-system-power`. |
| [xai-test-utils — Workspace crate](systems/xai-test-utils.md) | Module | Open when changing the `xai-test-utils` crate at `crates/common/xai-test-utils`. |
| [xai-token-estimation — Workspace crate](systems/xai-token-estimation.md) | Module | Open when changing the `xai-token-estimation` crate at `crates/codegen/xai-token-estimation`. |
| [xai-tool-protocol — Tool wire protocol](systems/xai-tool-protocol.md) | Module | Open when changing tool JSON-RPC envelopes or registration wire. |
| [xai-tool-runtime — Tool runtime dispatch](systems/xai-tool-runtime.md) | Module | Open when changing tool dispatch, streaming, or notifications. |
| [xai-tool-types — Tool type defs](systems/xai-tool-types.md) | Module | Open when changing shared tool types. |
| [xai-tracing-macros — Workspace crate](systems/xai-tracing-macros.md) | Module | Open when changing the `xai-tracing-macros` crate at `crates/codegen/xai-tracing-macros`. |
| [xai-tracing — Workspace crate](systems/xai-tracing.md) | Module | Open when changing the `xai-tracing` crate at `crates/common/xai-tracing`. |
| [xai-tty-utils — Workspace crate](systems/xai-tty-utils.md) | Module | Open when changing the `xai-tty-utils` crate at `crates/codegen/xai-tty-utils`. |
<!-- CONCEPT-MAP:END -->

## Change log

See [log.md](log.md) for chronological regeneration history.
