# AGENTS.md

Dimy owns this repo.
Work style: telegraph, minimal tokens.

## Delegation

- For repo bootstrap discipline (docs/tests/full gate/CI), use global skill: `~/.codex/skills/repo-bootstrap-gatekeeper`.
- Apply it when creating repos, scaffolding projects, or upgrading quality workflow.

## Local Protocol

- Workspace root: `~/Projects`.
- For missing `dimi20cen` repos, clone with HTTPS under `~/Projects`.
- For non-`dimi20cen` OSS repos, clone under `~/Projects/oss`.
- Ignore `CLAUDE.md`.
- Use `trash` for deletes.
- Keep edits small and reviewable.
- Prefer files under ~500 LOC; split when needed.
- Commit format: Conventional Commits (`feat|fix|refactor|build|ci|chore|docs|style|perf|test`).

## Git Safety

- Default safe commands first: `git status`, `git diff`, `git log`.
- Push only when user asks.
- No destructive ops unless explicitly requested (`reset --hard`, `clean`, `restore`, `rm`, etc.).
- No amend unless requested.
- Keep remotes under `~/Projects` on HTTPS.

## Verification

- Before handoff, run checks required by active repo gate.
- If blocked, report exact failing command, key error line, and what input/env is missing.

## Tools

- `gh` for PR/issue/CI interactions.
- `bin/browser-tools` for browser automation.
