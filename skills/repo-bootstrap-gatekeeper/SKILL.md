---
name: repo-bootstrap-gatekeeper
description: >-
  Initialize or upgrade software repositories with reliable engineering defaults.
  Use when creating a new repo, scaffolding a project, or improving delivery
  discipline so Codex must keep docs current, add risk-based tests, detect
  major changes, create missing gate commands, run full gate after major
  changes, generate missing GitHub Actions gate workflow, and hand off failures
  with a structured blocker report.
---

# Repo Bootstrap Gatekeeper

## Workflow

1. Inspect repository state.
- Detect stack from `package.json`, `pyproject.toml`, or `requirements*.txt`.
- Detect existing quality commands and CI workflows.
- Detect docs layout (`README.md`, `docs/`).

2. Apply docs-and-tests policy.
- Read `references/docs-and-tests-policy.md`.
- Update `README.md` when setup, usage, behavior, or API changes.
- Create or update `docs/changes.md` for non-trivial behavior/API changes.
- Add tests for risk-bearing changes; allow skips only with explicit justification.

3. Establish canonical gate commands.
- Read `references/gate-detection.md`.
- For JS/TS repos, ensure scripts for `lint`, `typecheck`, `test`, `docs`, and `gate`.
- For Python repos, ensure equivalent commands via existing task tooling or `scripts/gate.sh`.
- Preserve existing commands when valid; fill gaps only.

4. Detect major-change trigger.
- Run full gate when any trigger in `references/gate-detection.md` matches.
- Run scoped checks for minor changes.

5. Ensure CI parity.
- If `.github/workflows/gate.yml` is missing, add it from `assets/github-actions/` template closest to stack.
- Keep CI command aligned with local `gate` command.

6. Validate and hand off.
- Execute gate or scoped checks.
- If blocked, emit structured blocker report with:
  - checks attempted
  - pass/fail per check
  - exact failing command and key error line
  - blocker category
  - exact rerun command
  - required user input/secrets

## Resource Loading

- Read `references/docs-and-tests-policy.md` before editing docs/tests policy.
- Read `references/gate-detection.md` before creating or changing gate commands.
- Copy CI starting point from `assets/github-actions/` and adapt minimally.
