---
type: API
title: "Configuration surface"
description: >
  Open when changing config files, env vars, managed config, or CLI flags that affect runtime.
resource: "crates/codegen/xai-grok-config"
tags: [reference]
timestamp: "2026-07-15T23:15:13Z"
x-grounded-paths: ["crates/codegen/xai-grok-config/src/lib.rs", "crates/codegen/xai-grok-pager/docs/user-guide/05-configuration.md", "README.md"]
x-callers: []
---

# Configuration surface

## What it is

Configuration merges multiple layers (system managed → user managed → user config → signed requirements → MDM on macOS).

See `xai-grok-config` docs and user-guide/05-configuration.md for operator-facing keys.

Implementation lives at `crates/codegen/xai-grok-config`.

## How it works

```mermaid
flowchart TB
  Sys["/etc/grok/managed_config.toml"] --> Merge
  HomeM["$GROK_HOME/managed_config.toml"] --> Merge
  Home["$GROK_HOME/config.toml"] --> Merge
  Req["requirements.toml layers"] --> Merge
  Merge[xai-grok-config loader] --> Runtime[shell/pager runtime]
```

## See also

- [systems/xai-grok-config.md](../systems/xai-grok-config.md)
- [systems/xai-grok-tools.md](../systems/xai-grok-tools.md)
- [overview/architecture.md](../overview/architecture.md)
- User guide under crates/codegen/xai-grok-pager/docs/user-guide/
