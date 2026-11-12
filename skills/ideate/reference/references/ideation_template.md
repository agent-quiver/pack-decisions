# Ideation document body template

Used by `/ideate` Step 3. Replace `NNN`, title, dates, and prose. Status for new
ideations is typically **Active**; other enum values are **Incorporated** |
**Superseded** | **Parked** | **Merged**.

```markdown
# NNN: [Title]

**Date:** YYYY-MM-DD
**Status:** Active   <!-- one of: Active | Incorporated | Superseded | Parked | Merged -->
**Author:** [user or inferred]

## Problem Statement

What's broken, missing, or suboptimal? Be specific and honest.

## Prior Art

What exists today? Competing approaches, existing tools, prior attempts.
For each: what works, what doesn't, and why.

## Proposed Approach

The recommended path forward. Distinguish clearly:
- **Proven:** We know this works because [evidence]
- **Likely:** Strong reasons to believe this works
- **Aspirational:** We hope this works but have no evidence yet

## Trade-offs

What do we gain? What do we give up? What risks remain?

## Risks & Pre-mortem

Imagine this failed six months from now. What killed it? Name the *specific* assumption
that broke first — not a generic failure mode. One or two paragraphs.

## Action Items

- [ ] Concrete next steps to validate or implement this idea

## Open Questions

Questions that must be answered before implementation.
```
