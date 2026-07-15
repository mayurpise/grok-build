---
type: Runbook
title: "Getting started"
description: >
  Stable wiki-root alias for onboarding. Prefer this path when linking
  getting-started.md without a section prefix.
resource: README.md
tags: [runbook, onboarding, alias]
timestamp: "2026-07-15T23:20:00Z"
x-grounded-paths: ["README.md", "rust-toolchain.toml"]
x-callers: []
---

# Getting started

This file is a **stable alias** at `wiki/getting-started.md` so links that use
the bare name resolve.

## Full onboarding

- **Draft root (recommended):** [../getting-started.md](../getting-started.md)
- **Build & run:** [overview/getting-started.md](overview/getting-started.md)
- **Product / user guide:** [features/getting-started.md](features/getting-started.md)

## Quick commands

```sh
# Install
curl -fsSL https://x.ai/cli/install.sh | bash
grok --version

# From this repo
cargo run -p xai-grok-pager-bin
```
