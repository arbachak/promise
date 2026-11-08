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

- When coordinating code review, including before a pull request is ready to merge, read [requesting-code-review](.agents/skills/requesting-code-review/SKILL.md) and follow its workflow. Give the reviewer the requirements and the complete change range.
- For explanations of code, changes, concepts, or a period of work, read [ce-explain](.agents/skills/ce-explain/SKILL.md) and the references it requires. Follow its procedure for the behavior-trace and work-recap helpers when needed.
- Keep upstream skill files and their license unchanged. Record their source revision and checksums in [.agents/upstream-lock.json](.agents/upstream-lock.json).
- Explaining a subject does not authorize fixes or external publication. Deliver artifacts only to the destination authorized for the task.
