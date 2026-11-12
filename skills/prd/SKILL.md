---
name: prd
description: "Plan a change as a PRD with implementable user stories and acceptance criteria. Writes ops/prd/NNN_slug/NNN_slug_prd.md."
---

# /prd

1. Read the ideation and ADR it implements. Ask at most three clarifying questions if scope is unclear.
2. **Number** the next `NNN` in `ops/prd/` (from 001). Stories are `US-NNN.n`, numbered locally.
3. **Write** `NNN_slug/NNN_slug_prd.md`:
   ```
   # PRD-NNN — <title>
   date · status: draft | active | closed (vX.Y.Z) · implements: ADR-NNN
   ## Why           the outcome, measurable
   ## Scope / Non-goals
   ## Stories
   ### US-NNN.n — <title>  · size S|M|L · depends on: …
   As <who>, I need <what>, so that <why>.
   **Acceptance:** numbered, checkable criteria (a test, a command, a measured number).
   **Gate:** the targeted tests + mypy + ruff for touched files.
   **Commit:** <sha — filled in when done>
   ## Verification   how the whole PRD is shown to work (live run, measurement, scoreboard)
   ## Closeout       full make check · CHANGELOG · tag vX.Y.Z · the verification evidence pasted here
   ```
   Sizes: S ≤ 2 files / 50 lines; M ≤ 4 files / 200; L ≤ 8 files / 500. Split anything larger.
4. Index it in `prd/INDEX.md`. Report: path, story count, order, total size.

## Layout

Paths above follow the lab layout in `standards.docs`: `docs/` is the product as
it is, `ops/` is the working trail. If the tree's `AGENTS.md`/`CLAUDE.md` names
other homes, use those.

## Supporting files

`reference/references/prd_body_template.md`: a full PRD body template.
