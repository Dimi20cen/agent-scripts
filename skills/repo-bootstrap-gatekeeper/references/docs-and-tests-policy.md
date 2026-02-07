# Docs and Tests Policy

## Docs Requirements

Apply all rules below.

1. Update `README.md` when behavior, setup, API, or usage changes.
2. Maintain `docs/changes.md` for non-trivial behavior/API changes.
3. Create `docs/` if missing.
4. Use concise entries in `docs/changes.md`:
- Date (`YYYY-MM-DD`)
- Summary of change
- Affected files
- Migration notes (if any)
- Validation status

## Test Requirements (Risk-Based)

Add or update tests when any of these are true.

1. Runtime logic changed.
2. Bugfix changed behavior.
3. Public API/schema/contract changed.
4. Data parsing, transformation, or validation changed.

Test update may be skipped only for:

1. Docs-only changes.
2. Pure formatting/style changes.
3. Non-functional scaffolding with no runtime-path change.

When skipping tests, include one-line rationale in handoff.

## Handoff Requirements

If checks fail or cannot run, provide structured blocker report with:

1. Checks attempted.
2. Pass/fail status for each check.
3. Exact command that failed.
4. Key error excerpt.
5. Blocker class (`env`, `network`, `flaky`, `dependency`, `tooling-gap`).
6. Exact rerun command.
7. Needed user input or secret.
