# Changes

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
