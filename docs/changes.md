# Changes

## 2026-02-14

- Finalized AGENTS-only mode by removing `skills/` from the repository.
- Removed global compatibility artifacts from `~/.codex/skills/` (`repo-bootstrap-gatekeeper` symlink and backup folder).
- Updated docs to remove current-state references to optional skill wrappers.
- Added explicit AGENTS value statements favoring stable/tested technology choices over trends.
- Expanded gate contract with explicit `secrets` and `dependencies` checks.
- Affected files: `AGENTS.md`, `README.md`, `docs/changes.md`.
- Migration notes: canonical instructions now live only in `AGENTS.md`.
- Validation: verified `~/.codex/skills/` cleanup and local repository layout.

## 2026-02-13

- Simplified repository to AGENTS-first guidance with core bootstrap policy embedded directly in `AGENTS.md`.
- Reworked `README.md` to pointer-style usage and minimal layout documentation.
- Flattened `skills/repo-bootstrap-gatekeeper` by keeping only `SKILL.md`; removed `agents/`, `assets/github-actions/`, and `references/`.
- Affected files: `AGENTS.md`, `README.md`, `docs/changes.md`, `skills/repo-bootstrap-gatekeeper/SKILL.md`.
- Migration notes: use `AGENTS.md` as canonical policy source; keep skill wrapper optional.
- Validation: local path/layout verification and git diff review.

## 2026-02-07

- Added global skill delegation in `AGENTS.md` to enforce repo bootstrap quality rules.
- Scope: docs + tests policy, major-change full-gate execution, and CI gate alignment.
- Affected files: `AGENTS.md`, `README.md`, `docs/changes.md`.
- Migration notes: none.
- Validation: skill validation and git checks completed.

## 2026-02-07 (instruction-home update)

- Moved canonical skill source into repo at `skills/repo-bootstrap-gatekeeper`.
- Set runtime location to symlink from `~/.codex/skills/repo-bootstrap-gatekeeper`.
- Updated docs and AGENTS guidance to make `agent-scripts` the single source of truth.
- Migration notes: previous runtime folder preserved as timestamped backup under `~/.codex/skills/`.
- Validation: symlink target exists and skill validation passes.
