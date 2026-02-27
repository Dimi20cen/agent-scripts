# AGENTS.md

Dimi owns this repo.


## Agent Protocol

- Use `trash` for deletes.
- Keep edits small/reviewable.
- Prefer files under ~500 LOC; split when needed.
- Bugs: add regression test when it fits.
- Prefer end-to-end verify; if blocked, say what’s missing.
- New deps: quick health check (recent releases/commits, adoption).

## Values

- Prefer stable, well-maintained, battle-tested frameworks/libraries over short-lived trends.
- Prefer choices that reduce long-term maintenance risk and support easy future cold starts.


## Docs

- Open docs before coding.
- Follow links until domain makes sense; honor Read when hints.
- Keep notes short; update docs when behavior/API changes (no ship w/o docs).
- Add read_when hints on cross-cutting docs.


### Build / Test

- Before handoff: run full gate (lint/typecheck/tests/docs).
- Keep it observable (logs, panes, tails, MCP/browser tools).


## Git

- Safe by default: git status/diff/log. Push or branch change only when user asks.
- Destructive ops forbidden unless explicit (reset --hard, clean, restore, rm, …).
- Don’t delete/rename unexpected stuff; stop + ask.


## Critical Thinking
- Fix root cause (not band-aid).
- Unsure: read more code; if still stuck, ask w/ short options.
- Conflicts: call out; pick safer path.
- Leave breadcrumb notes in thread.

<frontend_aesthetics> Avoid “AI slop” UI. Be opinionated + distinctive.

Do:

Typography: pick a real font; avoid Inter/Roboto/Arial/system defaults.
Theme: commit to a palette; use CSS vars; bold accents > timid gradients.
Motion: 1–2 high-impact moments (staggered reveal beats random micro-anim).
Background: add depth (gradients/patterns), not flat default.
Avoid: purple-on-white clichés, generic component grids, predictable layouts. </frontend_aesthetics>
