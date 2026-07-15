---
project: "grok-build"
module: "root"
generated_by: "draft:init"
generated_at: "2026-07-15T23:20:00Z"
---

# Getting Started — Grok Build

Canonical onboarding for this repo. Wiki mirrors:

- **Build / run from source:** [wiki/overview/getting-started.md](wiki/overview/getting-started.md)
- **Product install & first use:** [wiki/features/getting-started.md](wiki/features/getting-started.md)
- **User guide (full):** `crates/codegen/xai-grok-pager/docs/user-guide/01-getting-started.md`

---

## Install the released binary

```sh
curl -fsSL https://x.ai/cli/install.sh | bash   # macOS / Linux / Git Bash
irm https://x.ai/cli/install.ps1 | iex          # Windows PowerShell
grok --version
```

```sh
grok update   # later updates
```

## First launch

```sh
grok
```

On first launch the CLI opens a browser to authenticate with grok.com and stores credentials under `~/.grok/auth.json`.

API key (CI / no browser):

```sh
export XAI_API_KEY="xai-..."
grok
```

## Build from this repository

Requirements: Rust (`rust-toolchain.toml`, channel 1.92.0), `protoc` via `bin/protoc` or `$PROTOC` / PATH. macOS and Linux are primary hosts.

```sh
cargo run -p xai-grok-pager-bin              # build + launch TUI
cargo build -p xai-grok-pager-bin --release  # target/release/xai-grok-pager
cargo check -p xai-grok-pager-bin
```

The binary artifact is `xai-grok-pager`; official installs ship it as `grok`.

### Per-crate development loop

```sh
cargo check -p <crate>
cargo test -p <crate>
cargo clippy -p <crate>
cargo fmt --all
```

Prefer targeted crates — full-workspace builds are slow. Root `Cargo.toml` is **generated**; edit per-crate manifests only.

## Basic usage (TUI)

- Type a prompt and press `Enter`.
- `@path` attaches files (fuzzy picker).
- Permissions: approve tools as prompted, or `Ctrl+O` / `grok --yolo` / `/always-approve`.
- Headless: `grok -p "your prompt"`.
- ACP / IDE: `grok agent stdio` (see [agent mode](wiki/features/agent-mode-acp.md)).

## Key paths in this monorepo

| Path | Role |
|------|------|
| `crates/codegen/xai-grok-pager-bin` | Composition root / binary |
| `crates/codegen/xai-grok-pager` | TUI |
| `crates/codegen/xai-grok-shell` | Agent runtime |
| `crates/codegen/xai-grok-tools` | Tools |
| `crates/codegen/xai-grok-workspace` | FS / permissions / host |

Draft context: [index.md](index.md) · [wiki/index.md](wiki/index.md) · [architecture.md](architecture.md)

## See also

- [Authentication feature](wiki/features/authentication.md)
- [Permissions and safety](wiki/features/permissions-and-safety.md)
- [Build runbook](wiki/reference/build-runbook.md)
- [Entrypoint](wiki/entrypoints/main.md)
- Online docs: https://docs.x.ai/build/overview
