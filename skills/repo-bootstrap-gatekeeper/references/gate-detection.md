# Gate Detection and Creation (JS/TS + Python)

## Major-Change Heuristic

Treat change as major when any condition is true.

1. Four or more tracked files changed.
2. Changed path includes one of:
- `src/`
- `app/`
- `backend/`
- `api/`
- `db/`
- `migrations/`
- `schema/`
- `infra/`
3. Dependency or config files changed:
- `package.json`
- lockfiles
- `pyproject.toml`
- `requirements*.txt`
- `.github/workflows/*`
- Docker files
4. Public API/CLI/schema surface changed.
5. Bugfix touched runtime logic.

## Canonical Gate Contract

Ensure these logical checks exist:

1. `lint`
2. `typecheck`
3. `test`
4. `docs`
5. `gate` (runs checks above in order)

## JS/TS Strategy

1. If `package.json` exists, use npm scripts as canonical interface.
2. Preserve existing scripts if they already implement a check.
3. Fill missing scripts with project-appropriate commands.
4. Define `gate` as a deterministic chain of `lint`, `typecheck`, `test`, `docs`.

## Python Strategy

1. Prefer existing task runner (`make`, `tox`, `nox`, `poetry`, `hatch`, `uv`).
2. If no canonical gate exists, create `scripts/gate.sh` and wire checks.
3. Reuse currently configured tools where present.

## Unsupported Stack Fallback

1. Run discovered checks only.
2. Report unsupported stack gap explicitly.
3. Include recommended next command for user.
