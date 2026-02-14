# agent-scripts

Canonical guardrails for Codex workflows.

## Purpose

This repo is AGENTS-first. Shared behavior lives in `AGENTS.md`.

## Pointer-Style Usage

- Canonical instructions: `~/Projects/meta/agent-scripts/AGENTS.md`.
- Downstream repos should start with:
  - `READ ~/Projects/meta/agent-scripts/AGENTS.md BEFORE ANYTHING (skip if missing).`
- Add repo-local rules below that pointer line only when needed.

## Repository Layout

- `AGENTS.md`: shared guardrails and repo-bootstrap policy (docs/tests/gate/CI/handoff).
- `docs/changes.md`: changelog for non-trivial instruction updates.

## Simplification Rule

- Keep instructions portable and lightweight.
- Avoid extra packaging layers and template sprawl.
- If policy is core and stable, prefer keeping it directly in `AGENTS.md`.
