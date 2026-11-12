# PRD body template

Used by `/prd` Step 3. Replace placeholders; nest directory layout per Step 4 of the skill.

```markdown
# PRD-NNN: [Feature Name]

**Date:** YYYY-MM-DD
**Status:** Draft   <!-- one of: Draft | In Progress | Complete | Superseded | Dropped -->
**Ideation:** NNN (link to ideation document, if applicable)
**Stories:** US-XXX through US-YYY

## Context

What problem does this solve? Why now?

## User Stories

### US-XXX: Story title
**Complexity:** S | M | L
**Acceptance Criteria:**
- [ ] Criterion 1
- [ ] Criterion 2

**Test Plan:** How to verify this story works.

**Dependencies:** US-YYY (if any)

---

(repeat for each story)

## Dependencies

What must exist before this PRD can start?

## Verification

How do we know the whole PRD is done? The end-to-end acceptance test.

## Closure

Filled at PRD-write time, refined at PRD-close. Whoever closes the PRD
walks this section instead of re-deriving it from commits.

### Changelog entry (drafted now, refined at close)

One bullet per user-visible change. Cite US-NNN. Mark "BREAKING:" when applicable.
These bullets land in `CHANGELOG.md` under the new release heading at PRD close.

- <e.g. "Added `target_field` to domain.yaml relations; natural-key joins now resolve to declared text columns instead of integer surrogate PKs (US-639, US-640)">

### Closure checklist (orchestrator walks)

- [ ] All US-NNN flipped to `done`
- [ ] PRD `Status:` → `Complete`
- [ ] If linked to an ideation, ideation `Status:` → `Incorporated`
- [ ] `uv run python scripts/gen_indexes.py` run **immediately after** the two
      status flips above, in the SAME commit as everything else in this
      checklist. The status flips change what `docs/tasks/`'s (and
      `docs/ideation/`'s, if touched) generated `INDEX.md`/`ARCHIVE.md`/
      `index.json` must contain — skipping this step has broken the tagged
      commit's own CI pipeline twice already (PRD-354 → v0.199.0 → pipeline
      4954; PRD-356 → v0.200.0 → pipeline 4991), both times on the identical
      rule-23 registry-sync gate, both times requiring a hand-cut patch-bump
      re-tag to recover. `uv run python scripts/gen_indexes.py --check` must
      be clean on the final closure-commit tree before tagging (re-run it
      after every edit below too, not just once here).
- [ ] CHANGELOG.md updated: changelog bullets appended under `## [Unreleased]`,
      then `## [Unreleased]` cut into `## [vX.Y.Z] — YYYY-MM-DD` (single release
      SemVer tag per close — ticket-469 retired the CalVer `v2026.MM.DD.N` scheme)
- [ ] Closeout story `feat()` commit carries the `_PRODUCT_VERSION` + root-`pyproject`
      bump (via `python -m scripts.lib.version_bump --bump patch`) **before** the tag step.
      This bump is **mandatory** — the SemVer tag IS the release identity, so
      skipping it means the release cannot be tagged (the tagger refuses to
      re-cut an existing tag on a different commit). (A post-hoc wrapper cannot
      do this: amending is forbidden by `git.md`; a separate bump commit is
      invisible to `scan_commits`/`build_plan`, so the tag would land on the
      old feat commit whose tree still carries the stale version.) The same
      invocation also diff-driven patch-bumps every `packages/<pkg>/` changed
      since the previous release tag (ticket-470) — stage all files it
      modified, not just the two product-version files.
- [ ] Consumer-surface prose-drift gate: run
      `uv run python scripts/check_guide_drift.py` **before** tagging
      (US-350.1, ticket-1002). Fails when the rendered MCP intent guide
      changed since the previous release tag with no `CHANGELOG.md` citation
      in the same commit range, or when a new user-settable wire field
      shipped (rule 45's `_WIRE_FIELD_RENDER_ORDER` set grew) while the guide
      stayed byte-identical — the [[667]]/ticket-1009 class. A red result
      means: teach the capability in the guide, or add the CHANGELOG.md
      citation, before tagging.
- [ ] `uv run python scripts/tag-prd.py NNN --apply` executed (or `make release PRD=NNN APPLY=1`)
      — cuts ONE annotated release tag `vX.Y.Z`, no CalVer/umbrella twin
- [ ] Tag exists and lists every US-NNN — verify with `git show vX.Y.Z`
```
