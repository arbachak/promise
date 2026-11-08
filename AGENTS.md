# promise

## Project

- This is a Go library with a minimum version of Go 1.25.0. Read `go.mod` for the development toolchain.
- Keep the library and its tests free of external Go module dependencies. Use ordinary Go build and test commands.

## Working agreements

- Perform the agreed task and preserve other people's changes. Analysis or explanation alone does not authorize edits.
- Check the branch and working tree before editing. Take commands and tool versions from the project files and `README.md`.
- Work on a separate branch and open a pull request into `main`. Commit and push within the user's authorized scope; merge only when explicitly requested.
- Run checks appropriate to the change and review the final diff. Report actual results and limitations; passing Go CI does not verify an agent skill.
- Keep task context in `D:\obsidian\promise`: read related notes before resuming and save verified decisions, results, and next steps after significant milestones. Do not commit these local notes.
- Write project instructions in English and discuss changes and maintain local notes in Russian.

## Local skills

- For branch naming and creation, follow [conventional-branch](.agents/skills/conventional-branch/SKILL.md).
- Use AI-agent branch prefixes only when explicitly requested by the user; otherwise use a purpose-based prefix. This overrides the skill's agent-prefix recommendation.
- For the TDD implementation phase, the coordinating agent dispatches the registered [tdd-implementer profile](.codex/agents/tdd-implementer.toml) with `fork_turns="none"`, without model or reasoning-effort overrides, supplying the absolute repo_root, task scope, assigned files, requirements, and acceptance checks. When already running as tdd-implementer, execute the assignment directly without delegating again. If the host cannot select the registered profile, report that limitation instead of silently substituting a generic agent or manual model settings.
- For authorized Go feature work, bug fixes, and observable behavior changes, follow [test-driven-development](.agents/skills/test-driven-development/SKILL.md) and read its [writing-good-tests.md](.agents/skills/test-driven-development/writing-good-tests.md) reference before writing or changing tests. Use the project's Go commands, version floor, and dependency constraints. Mechanical documentation/configuration changes do not require artificial behavioral tests.
- The TDD implementation phase owns only the assigned code, tests, necessary refactoring, and local verification. Preserve pre-existing user changes. Finish that phase with uncommitted edits and a report of changed paths, observed RED/GREEN evidence, verification results, and limitations; do not stage, commit, switch branches, push, open a PR, or dispatch a reviewer as part of this phase.
- The coordinating workflow separately owns branch preparation, commits, requesting-code-review, review follow-up, publication, and CI. The TDD skill does not replace the registered code-reviewer or the existing Git workflow.
- When coordinating code review, including before a pull request is ready to merge, read [requesting-code-review](.agents/skills/requesting-code-review/SKILL.md) and follow its workflow. Give the reviewer the requirements and the complete change range.
- For that workflow, use the [code-reviewer profile](.codex/agents/code-reviewer.toml) in place of the upstream generic subagent. Keep the upstream reviewer prompt as the source of review criteria; report when the host cannot select the registered profile.
- For explanations of code, changes, concepts, or a period of work, read [ce-explain](.agents/skills/ce-explain/SKILL.md) and the references it requires. Follow its procedure for the behavior-trace and work-recap helpers when needed.
- Keep upstream skill files and their license unchanged. Record their source revision and checksums in [.agents/upstream-lock.json](.agents/upstream-lock.json).
- Explaining a subject does not authorize fixes or external publication. Deliver artifacts only to the destination authorized for the task.
