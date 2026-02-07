# agent-scripts

Scripts and conventions for Codex-driven repository workflows.

## Purpose

This repository is the canonical home for your agent instructions and reusable skills.

## Includes

- Local `AGENTS.md` conventions for this repo.
- Reusable skill: `skills/repo-bootstrap-gatekeeper`.
- Runtime symlink target: `~/.codex/skills/repo-bootstrap-gatekeeper` -> `~/Projects/agent-scripts/skills/repo-bootstrap-gatekeeper`.

## Gatekeeper Skill

The gatekeeper skill enforces:

- docs updates during coding (`README.md` + `docs/changes.md`)
- risk-based test updates
- full-gate execution after major changes
- CI gate generation/alignment
