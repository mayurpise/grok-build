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

# Development Workflow

| Field | Value |
|-------|-------|
| **Branch** | `main` → `origin/main` |
| **Commit** | `b189869` |
| **Generated** | 2026-07-15T23:08:34Z |
| **Synced To** | `b189869b7755d2b482969acf6c92da3ecfeffd36` |

---

## Test-Driven Development

**Mode:** flexible

**Coverage Target:**
```yaml
coverage_target: 0  # No global enforced % in OSS tree; prefer targeted tests per change
```

### Flexible TDD
- [x] Tests required for non-trivial behavior changes before marking complete
- [x] Prefer reproducing bugs with a failing test first when practical
- [x] Snapshot/UI changes use insta intentionally
- [ ] Strict RED-GREEN for every one-liner not required

## Commit Strategy

**Format:** conventional commits preferred (`type(scope): description`)

### Types
| Type | Use For |
|------|---------|
| `feat` | New feature |
| `fix` | Bug fix |
| `docs` | Documentation only |
| `refactor` | Structure without behavior change |
| `test` | Tests only |
| `chore` | Tooling / deps |

### Frequency
- Small, reviewable commits; this OSS tree is a sync publish surface — external PRs not accepted.

## Validation

```yaml
auto_validate: true
blocking:
  - cargo check -p <touched-crate>
  - cargo test -p <touched-crate>
preferred:
  - cargo clippy -p <touched-crate>
  - cargo fmt --all
avoid:
  - full-workspace cargo build unless necessary (slow)
```

## Review

- Internal review process (external contributions not accepted).
- Security reports via SECURITY.md, not public issues for vulns.

## Draft tracks

- Use `/draft:new-track` for feature/bug planning inside this repo context.
- `/draft:init refresh` after large structural changes.
