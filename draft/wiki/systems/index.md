---
title: "systems"
---

# systems

## Concept Map

<!-- CONCEPT-MAP:START -->
| Concept | Type | Routing description |
|---------|------|---------------------|
| [build — proto build helpers](build.md) | Module | Open when fixing protoc discovery, protobuf codegen build scripts, or hermetic builds that depend on bin/protoc. |
| [cargo — graph label → see xai-grok-pager-bin](cargo.md) | Module | Graph package label `cargo` is low-fidelity. Prefer the real crate page `xai-grok-pager-bin`. Cargo workspace root is generated; start from composition root crate. |
| [cli-chat-proxy-types — Chat proxy types](cli-chat-proxy-types.md) | Module | Open when changing CLI↔proxy serde contracts. |
| [codegen — primary CLI crate closure](codegen.md) | Module | Open when changing the Grok CLI/TUI, agent runtime, tools, workspace, config, MCP, markdown, auth, or sampler. Parent of all crates/codegen/* pages. |
| [common — shared leaf crates](common.md) | Module | Open when working on tool protocol/runtime, compaction, circuit breakers, computer-hub, or shared tracing under crates/common/. |
| [dagre_rust — Dagre layout](dagre-rust.md) | Module | Open when fixing graph layout in Mermaid stack. |
| [dict — graph label → see xai-grok-config](dict.md) | Module | Graph package label `dict` is low-fidelity. Prefer the real crate page `xai-grok-config`. Map-like settings live in config types — not a package boundary. |
| [graphlib_rust — Graphlib](graphlib-rust.md) | Module | Open when changing graph primitives for Mermaid. |
| [int — graph label → see xai-token-estimation](int.md) | Module | Graph package label `int` is low-fidelity. Prefer the real crate page `xai-token-estimation`. Numeric helpers are scattered; token estimation is one real crate. |
| [list — graph label → see xai-grok-shell](list.md) | Module | Graph package label `list` is low-fidelity. Prefer the real crate page `xai-grok-shell`. List UIs live in pager/shell session listing — not a package boundary. |
| [mc — cli-chat-proxy shared types](mc.md) | Module | Open when changing wire types shared with the cli-chat-proxy backend: session metadata, sandbox flags, feedback, subagent bundles, deployment config. |
| [mermaid-to-svg — Mermaid→SVG](mermaid-to-svg.md) | Module | Open when fixing diagram SVG rendering (vendored). |
| [ordered_hashmap — Ordered map](ordered-hashmap.md) | Module | Open when fixing order-sensitive maps in Mermaid stack. |
| [profile — graph label → see xai-grok-shell-base](profile.md) | Module | Graph package label `profile` is low-fidelity. Prefer the real crate page `xai-grok-shell-base`. CPU profiling lives in shell-base; --agent-profile is CLI path resolution. |
| [ptyctl-cli — PTY control CLI](ptyctl-cli.md) | Module | Open when changing ptyctl command-line. |
| [ptyctl — PTY control lib](ptyctl.md) | Module | Open when changing PTY control primitives. |
| [str — graph label → see xai-grok-secrets](str.md) | Module | Graph package label `str` is low-fidelity. Prefer the real crate page `xai-grok-secrets`. String/secret handling is not a package; see secrets sanitizer and string-heavy crates. |
| [workspace — graph label → see xai-grok-workspace](workspace.md) | Module | Graph package label `workspace` is low-fidelity. Prefer the real crate page `xai-grok-workspace`. Prefer the real `xai-grok-workspace` crate page. |
| [xai-acp-lib — ACP protocol lib](xai-acp-lib.md) | Module | Open when changing ACP gateway, channels, or message framing. |
| [xai-agent-lifecycle — Agent lifecycle](xai-agent-lifecycle.md) | Module | Open when changing agent start/stop/lifecycle contributors. |
| [xai-chat-state — Chat state actor](xai-chat-state.md) | Module | Open when changing conversation state, persistence, or compaction hooks. |
| [xai-circuit-breaker — Circuit breaker](xai-circuit-breaker.md) | Module | Open when changing open/half-open breaker policy. |
| [xai-codebase-graph — Code index graph](xai-codebase-graph.md) | Module | Open when changing tree-sitter index, goto-def/ref, or incremental reindex. |
| [xai-computer-hub-core — Computer hub core](xai-computer-hub-core.md) | Module | Open when changing hub tool registry/transport core. |
| [xai-computer-hub-mcp-adapter — Hub MCP adapter](xai-computer-hub-mcp-adapter.md) | Module | Open when bridging computer hub to MCP. |
| [xai-computer-hub-sdk — Computer hub SDK](xai-computer-hub-sdk.md) | Module | Open when changing hub client connection/handshake. |
| [xai-crash-handler — Workspace crate](xai-crash-handler.md) | Module | Open when changing the `xai-crash-handler` crate at `crates/codegen/xai-crash-handler`. |
| [xai-fast-worktree — Fast git worktrees](xai-fast-worktree.md) | Module | Open when changing CoW/BTRFS worktree creation or pools. |
| [xai-file-utils — File utilities](xai-file-utils.md) | Module | Open when changing shared file helpers. |
| [xai-fsnotify — FS notify](xai-fsnotify.md) | Module | Open when changing filesystem watchers. |
| [xai-gix-status — Workspace crate](xai-gix-status.md) | Module | Open when changing the `xai-gix-status` crate at `crates/codegen/xai-gix-status`. |
| [xai-grok-agent — Agent core helpers](xai-grok-agent.md) | Module | Open when changing agent-side helpers used by shell/pager. |
| [xai-grok-announcements — Workspace crate](xai-grok-announcements.md) | Module | Open when changing the `xai-grok-announcements` crate at `crates/codegen/xai-grok-announcements`. |
| [xai-grok-auth — Authentication](xai-grok-auth.md) | Module | Open when changing OIDC/browser auth or token refresh. |
| [xai-grok-compaction — Context compaction](xai-grok-compaction.md) | Module | Open when changing intra/inter/history/code compaction. |
| [xai-grok-config — Config loading/merge](xai-grok-config.md) | Module | Open when changing config.toml layers, managed config, or version overrides. |
| [xai-grok-config-types — Config type defs](xai-grok-config-types.md) | Module | Open when changing config schema types. |
| [xai-grok-env — Workspace crate](xai-grok-env.md) | Module | Open when changing the `xai-grok-env` crate at `crates/codegen/xai-grok-env`. |
| [xai-grok-hooks — Hooks runtime](xai-grok-hooks.md) | Module | Open when changing PreToolUse/session hooks discovery or execution. |
| [xai-grok-http — HTTP helpers](xai-grok-http.md) | Module | Open when changing shared HTTP client wrappers. |
| [xai-grok-markdown-core — Workspace crate](xai-grok-markdown-core.md) | Module | Open when changing the `xai-grok-markdown-core` crate at `crates/codegen/xai-grok-markdown-core`. |
| [xai-grok-markdown — Streaming markdown TUI](xai-grok-markdown.md) | Module | Open when changing markdown/code/math/mermaid rendering in scrollback. |
| [xai-grok-mcp — MCP integration](xai-grok-mcp.md) | Module | Open when changing MCP servers, OAuth, credentials, or rmcp quarantine. |
| [xai-grok-memory — Cross-session memory](xai-grok-memory.md) | Module | Open when changing MEMORY.md storage, dream/search, or experimental memory. |
| [xai-grok-mermaid — Mermaid integration](xai-grok-mermaid.md) | Module | Open when wiring Mermaid diagrams into markdown/TUI. |
| [xai-grok-models — Model catalog](xai-grok-models.md) | Module | Open when changing default model lists. |
| [xai-grok-pager-bin — Entrypoint composition root](xai-grok-pager-bin.md) | Module | Open when changing CLI binary startup, mode dispatch, jemalloc, or auto-update wiring. |
| [xai-grok-pager — Full-screen TUI](xai-grok-pager.md) | Module | Open when changing TUI scrollback, prompt, slash commands, modals, event loop, or pager UI. |
| [xai-grok-pager-minimal — Minimal scrollback-native mode](xai-grok-pager-minimal.md) | Module | Open when changing minimal pager mode seams or lightweight UI. |
| [xai-grok-pager-pty-harness — PTY harness / benches](xai-grok-pager-pty-harness.md) | Module | Open when changing PTY integration tests or paste-latency benches. |
| [xai-grok-pager-render — Pager render engine](xai-grok-pager-render.md) | Module | Open when changing terminal rendering, themes, or scrollback paint paths. |
| [xai-grok-paths — Workspace crate](xai-grok-paths.md) | Module | Open when changing the `xai-grok-paths` crate at `crates/codegen/xai-grok-paths`. |
| [xai-grok-plugin-marketplace — Plugin marketplace](xai-grok-plugin-marketplace.md) | Module | Open when changing plugin discovery/install marketplace. |
| [xai-grok-sampler — Model sampling/streaming](xai-grok-sampler.md) | Module | Open when changing HTTP streaming, retry, sampler actor, or model backends. |
| [xai-grok-sampling-types — Sampling shared types](xai-grok-sampling-types.md) | Module | Open when changing sampling event/type contracts. |
| [xai-grok-sandbox — OS sandbox](xai-grok-sandbox.md) | Module | Open when changing Landlock/Seatbelt profiles or child network policy. |
| [xai-grok-secrets — Secret sanitizer](xai-grok-secrets.md) | Module | Open when changing secret redaction. |
| [xai-grok-shared — Shared CLI helpers](xai-grok-shared.md) | Module | Open when changing cross-cutting shared utilities. |
| [xai-grok-shell-base — Shell base helpers](xai-grok-shell-base.md) | Module | Open when changing CPU profile, env helpers shared by shell. |
| [xai-grok-shell — Agent runtime](xai-grok-shell.md) | Module | Open when changing sessions, leader, headless/stdio agent, relay, or shell-side tool orchestration. |
| [xai-grok-shell-session-support — Workspace crate](xai-grok-shell-session-support.md) | Module | Open when changing the `xai-grok-shell-session-support` crate at `crates/codegen/xai-grok-shell-session-support`. |
| [xai-grok-subagent-resolution — Workspace crate](xai-grok-subagent-resolution.md) | Module | Open when changing the `xai-grok-subagent-resolution` crate at `crates/codegen/xai-grok-subagent-resolution`. |
| [xai-grok-telemetry — Telemetry engine](xai-grok-telemetry.md) | Module | Open when changing product events, OTEL, Sentry, or unified log. |
| [xai-grok-test-support — Workspace crate](xai-grok-test-support.md) | Module | Open when changing the `xai-grok-test-support` crate at `crates/codegen/xai-grok-test-support`. |
| [xai-grok-tools-api — Tools protobuf API](xai-grok-tools-api.md) | Module | Open when changing tools wire proto or generated API shapes. |
| [xai-grok-tools — Tool implementations](xai-grok-tools.md) | Module | Open when adding/changing tools (file, shell, search, web, skills, MCP use_tool). |
| [xai-grok-update — Auto-update](xai-grok-update.md) | Module | Open when changing binary update check/install. |
| [xai-grok-version — Workspace crate](xai-grok-version.md) | Module | Open when changing the `xai-grok-version` crate at `crates/codegen/xai-grok-version`. |
| [xai-grok-voice — Voice input](xai-grok-voice.md) | Module | Open when changing voice capture/integration. |
| [xai-grok-workspace-client — Workspace client](xai-grok-workspace-client.md) | Module | Open when changing workspace client adapters. |
| [xai-grok-workspace — Host FS/VCS/permissions](xai-grok-workspace.md) | Module | Open when changing filesystem, permission pipeline, worktrees, foreign sessions, or hub. |
| [xai-grok-workspace-types — Workspace request types](xai-grok-workspace-types.md) | Module | Open when changing workspace RPC/request message types. |
| [xai-hooks-plugins-types — Workspace crate](xai-hooks-plugins-types.md) | Module | Open when changing the `xai-hooks-plugins-types` crate at `crates/codegen/xai-hooks-plugins-types`. |
| [xai-hunk-tracker — Hunk tracker actor](xai-hunk-tracker.md) | Module | Open when changing edit hunk tracking actors. |
| [xai-interjection-core — Workspace crate](xai-interjection-core.md) | Module | Open when changing the `xai-interjection-core` crate at `crates/common/xai-interjection-core`. |
| [xai-mixpanel — Workspace crate](xai-mixpanel.md) | Module | Open when changing the `xai-mixpanel` crate at `crates/codegen/xai-mixpanel`. |
| [xai-prompt-queue — Workspace crate](xai-prompt-queue.md) | Module | Open when changing the `xai-prompt-queue` crate at `crates/codegen/xai-prompt-queue`. |
| [xai-proto-build — Protoc finder](xai-proto-build.md) | Module | Open when fixing hermetic protoc discovery. |
| [xai-ratatui-inline — Workspace crate](xai-ratatui-inline.md) | Module | Open when changing the `xai-ratatui-inline` crate at `crates/codegen/xai-ratatui-inline`. |
| [xai-ratatui-textarea — Workspace crate](xai-ratatui-textarea.md) | Module | Open when changing the `xai-ratatui-textarea` crate at `crates/codegen/xai-ratatui-textarea`. |
| [xai-sqlite-journal — Workspace crate](xai-sqlite-journal.md) | Module | Open when changing the `xai-sqlite-journal` crate at `crates/codegen/xai-sqlite-journal`. |
| [xai-system-power — Workspace crate](xai-system-power.md) | Module | Open when changing the `xai-system-power` crate at `crates/codegen/xai-system-power`. |
| [xai-test-utils — Workspace crate](xai-test-utils.md) | Module | Open when changing the `xai-test-utils` crate at `crates/common/xai-test-utils`. |
| [xai-token-estimation — Workspace crate](xai-token-estimation.md) | Module | Open when changing the `xai-token-estimation` crate at `crates/codegen/xai-token-estimation`. |
| [xai-tool-protocol — Tool wire protocol](xai-tool-protocol.md) | Module | Open when changing tool JSON-RPC envelopes or registration wire. |
| [xai-tool-runtime — Tool runtime dispatch](xai-tool-runtime.md) | Module | Open when changing tool dispatch, streaming, or notifications. |
| [xai-tool-types — Tool type defs](xai-tool-types.md) | Module | Open when changing shared tool types. |
| [xai-tracing-macros — Workspace crate](xai-tracing-macros.md) | Module | Open when changing the `xai-tracing-macros` crate at `crates/codegen/xai-tracing-macros`. |
| [xai-tracing — Workspace crate](xai-tracing.md) | Module | Open when changing the `xai-tracing` crate at `crates/common/xai-tracing`. |
| [xai-tty-utils — Workspace crate](xai-tty-utils.md) | Module | Open when changing the `xai-tty-utils` crate at `crates/codegen/xai-tty-utils`. |
<!-- CONCEPT-MAP:END -->
