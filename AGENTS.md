# promise

## Project

- Go 1.25.0 or later. Use [go.mod](go.mod) for the development toolchain.
- Keep the library and its tests free of external Go module dependencies. Use ordinary Go build and test commands.

## Working agreements

- Stay within the user's request and preserve existing work. Explanation alone does not authorize edits or publication.
- Check Git state before editing. Use a separate branch and a PR into `main`; commit and push within the authorized scope, and merge only on explicit request.
- Use [README.md](README.md) for local commands and [CI](.github/workflows/ci.yml) for tool versions and additional checks.
- Run relevant checks, review the diff, and report actual results and limitations. Go CI does not validate agent skills.
- Write project documentation in English; discuss work and keep notes in Russian.
- Read project context in `D:\obsidian\promise` before resuming and update it after significant milestones; do not commit these notes.

## Local skills

Read the relevant skill and follow its references.

| Task | Skill | Registered agent |
| --- | --- | --- |
| Branch naming and creation | [conventional-branch](.agents/skills/conventional-branch/SKILL.md) | — |
| Go features, fixes and behavior changes | [test-driven-development](.agents/skills/test-driven-development/SKILL.md) | [tdd-implementer](.codex/agents/tdd-implementer.toml) |
| Code review, including before merge | [requesting-code-review](.agents/skills/requesting-code-review/SKILL.md) | [code-reviewer](.codex/agents/code-reviewer.toml) |
| Explain code, concepts or work | [ce-explain](.agents/skills/ce-explain/SKILL.md) | — |

Dispatch the registered agents with `fork_turns="none"` and no model or reasoning-effort overrides. Supply the absolute `repo_root`, task scope, assigned files, requirements and acceptance checks; for reviews, include the complete change range. Follow each profile's responsibilities. If a profile is unavailable, report the limitation instead of substituting another agent.

- Documentation-only and mechanical configuration changes do not require TDD.
- Use AI-agent branch prefixes only when explicitly requested by the user; otherwise use a purpose-based prefix. This overrides the skill's agent-prefix recommendation.
- Keep upstream skill files and licenses unchanged; record their revisions and checksums in [.agents/upstream-lock.json](.agents/upstream-lock.json).
