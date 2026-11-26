<!-- Block added by skill:init-repo to the AGENTS.md of a target repo. Source of truth: btmx-sdlc/docs/conventions.md -->

## How to develop in this repo

Work is tracked in GitHub Issues. Every change goes through an issue and a PR.

1. Pick an issue: `Task`, `Bug` or `Spike`. A `Story` has no code of its own; work on its Tasks.
2. Create the branch from the issue: `gh issue develop <n> --name <type>/<n>-<slug> --base main --checkout`.
3. Commit with Conventional Commits: `<type>[(scope)][!]: <description>`.
4. Open the PR with skill:pr. Do not write the PR title or body by hand.
5. The user merges the PR (squash only). Agents merge only when the user asks directly. The issue closes on merge. Close a Story by hand when all its Tasks are closed.

Create issues with skill:issue: it sets the issue type and, for a Task, the parent Story.

### Rules

- Issue types: `Story`, `Task` (sub-issue of a Story), `Bug`, `Spike`. 1 Task, Bug or Spike = 1 branch = 1 PR.
- Branch: `<type>/<n>-<slug>`. No commits on `main`.
- `<type>`: `feat`, `fix`, `refactor`, `perf`, `test`, `docs`, `style`, `build`, `ci`, `chore`, `revert`.
- Priority (issue field): set only when the user asks.

### Local checks

pre-commit hooks check the commit message and the branch name, and block commits on `main`. They are installed by skill:init-repo.
In a new clone run `pre-commit install`. Do not use `git commit --no-verify`.
