# AGENTS.md

Dimy owns this repo.
Work style: telegraph, minimal tokens.

## Canonical Home

- Shared instruction source: `~/Projects/meta/agent-scripts/AGENTS.md`.
- Downstream repos should start with:
  - `READ ~/Projects/meta/agent-scripts/AGENTS.md BEFORE ANYTHING (skip if missing).`
- Keep repo-specific rules below that pointer line.

## Agent Protocol

- Workspace root: `~/Projects`.
- Missing `dimi20cen` repo: clone with HTTPS under `~/Projects`.
- Non-`dimi20cen` OSS repo: clone under `~/Projects/oss`.
- Ignore `CLAUDE.md`.
- Use `trash` for deletes.
- Keep edits small/reviewable.
- Prefer files under ~500 LOC; split when needed.
- Commit format: Conventional Commits (`feat|fix|refactor|build|ci|chore|docs|style|perf|test`).

## Values

- Prefer stable, well-maintained, battle-tested frameworks/libraries over short-lived trends.
- Prefer choices that reduce long-term maintenance risk and support easy future cold starts.


## Critical Thinking
- Fix root cause (not band-aid).
- Unsure: read more code; if still stuck, ask w/ short options.
- Conflicts: call out; pick safer path.
- Leave breadcrumb notes in thread.

## Git Safety

- Safe first: `git status`, `git diff`, `git log`.
- Push only when user asks.
- No destructive ops unless explicitly requested (`reset --hard`, `clean`, `restore`, `rm`, etc.).
- No amend unless requested.
- Keep remotes under `~/Projects` on HTTPS.
- If unrelated changes appear unexpectedly, stop and ask.

## Repo Bootstrap Core

Apply this when creating repos, scaffolding projects, or upgrading repo quality workflow.

### Docs Policy

1. Update `README.md` when behavior, setup, API, or usage changes.
2. Maintain `docs/changes.md` for non-trivial behavior/API changes.
3. Create `docs/` if missing.
4. Keep each `docs/changes.md` entry concise:
   - Date (`YYYY-MM-DD`)
   - Summary
   - Affected files
   - Migration notes (if any)
   - Validation status

### Test Policy (Risk-Based)

Create `tests/` if missing.

Add/update tests when any is true:

1. Runtime logic changed.
2. Bugfix changed behavior.
3. Public API/schema/contract changed.
4. Data parsing/transformation/validation changed.

Allowed test-skip cases:

1. Docs-only changes.
2. Pure formatting/style changes.
3. Non-functional scaffolding with no runtime path change.

When skipping tests, include one-line rationale in handoff.


### Gate Contract

Canonical logical checks:

1. `lint`
2. `typecheck`
3. `test`
4. `docs`
5. `secrets`
6. `dependencies`
7. `gate` (runs checks above in deterministic order)

JS/TS:

1. Use `package.json` scripts as canonical interface.
2. Preserve valid existing scripts.
3. Fill missing scripts.
4. Define deterministic `gate`.

Python:

1. Prefer existing task runner (`make`, `tox`, `nox`, `poetry`, `hatch`, `uv`).
2. If no canonical gate exists, create `scripts/gate.sh`.
3. Reuse existing configured tools.

Secrets:

1. Ensure no secrets are committed (keys/tokens/credentials/.env).
2. If repo has a configured scanner (for example `gitleaks`, `trufflehog`, or equivalent), run it as part of `gate`.

Dependencies:

1. Ensure dependency manifests/lockfiles are updated when imports/runtime deps change.
2. No undeclared runtime dependencies.
3. If repo has a standard dependency/security audit check, include it in `gate`.

### CI Parity

- Keep CI command aligned with local `gate` command.
- If `.github/workflows/gate.yml` is missing, add a minimal workflow matching stack/runtime.

### Validation and Blockers

- Major change: run full gate.
- Minor change: run scoped checks.
- If blocked, hand off with:
  1. Checks attempted
  2. Pass/fail per check
  3. Exact failing command
  4. Key error line
  5. Blocker class (`env`, `network`, `flaky`, `dependency`, `tooling-gap`)
  6. Exact rerun command
  7. Required input/secret


## Tools

### gh
- GitHub CLI for PRs/CI/releases. Given issue/PR URL (or `/pull/5`): use `gh`, not web search.
- Examples: `gh issue view <url> --comments -R owner/repo`, `gh pr view <url> --comments --files -R owner/repo`.

### trash
- Move files to Trash: `trash …` (system command).

<frontend_aesthetics>
Avoid “AI slop” UI. Be opinionated + distinctive.

Do:
- Typography: pick a real font; avoid Inter/Roboto/Arial/system defaults.
- Theme: commit to a palette; use CSS vars; bold accents > timid gradients.
- Motion: 1–2 high-impact moments (staggered reveal beats random micro-anim).
- Background: add depth (gradients/patterns), not flat default.

Avoid: purple-on-white clichés, generic component grids, predictable layouts.
</frontend_aesthetics>
