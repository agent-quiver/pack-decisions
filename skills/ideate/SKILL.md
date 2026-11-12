---
name: ideate
description: "Explore a problem before deciding: forces, options, evidence, prior art, a recommendation. Writes ops/ideation/NNN_slug.md."
---

# /ideate

Use before a decision that is costly to reverse, or when a problem has more than one plausible shape.

**A project's first ideation (001) is its founding document, and it looks only forward.** It sets the
aspirational path: what the product is for, who it serves, the bets it makes, the hypotheses that could prove it
wrong (each with a measure and a failure condition), the milestones a user would notice, what success looks like,
and what it will not be. It does not look back: no "today it lives in…", no "extracted from…", no account of
an old system's defects. Everything else — ADRs, PRDs, research — follows from it. Operational context (where
the initial code comes from, what must be untangled) belongs in a research note or the PRD that does the work.
Shape for 001: Aspiration · Who it serves · What it makes · The bets · Hypotheses (table) · The path ·
What success looks like · What it will not be · Open questions · What follows.

For every later ideation:

1. **Number:** next `NNN` in `ops/ideation/` (start at 001). Never reuse.
2. **Write** `NNN_slug.md`:
   ```
   # Ideation NNN — <title>
   date: <YYYY-MM-DD> · status: open | decided (→ ADR-NNN) | parked
   ## The problem          what hurts, for whom, measured where possible
   ## Forces               what any answer must respect (laws, contracts, costs)
   ## Options              2–4, each with what it costs and what it buys
   ## Evidence             measurements, file:line, prior art — each labelled measured | read | assumed
   ## Recommendation       one, with the condition that would change it
   ## Open questions       each with who decides
   ```
3. **Index:** add a line to the folder's `INDEX.md`.

## Layout

Paths above follow the lab layout in `standards.docs`: `docs/` is the product as
it is, `ops/` is the working trail. If the tree's `AGENTS.md`/`CLAUDE.md` names
other homes, use those.

## Supporting files

`reference/methods.md`: five deep-exploration techniques to offer before drafting.
`reference/references/ideation_template.md`: a full ideation template.
