---
name: adr
description: "Record an architectural decision: context, decision, consequences, alternatives. Writes ops/adr/ADR-NNN-slug.md."
---

# /adr

An ADR records a decision **the user has made** (or a seat has made inside its own authority). A proposal waiting
for the user is `status: proposed` and says who must decide.

```
# ADR-NNN — <decision in one line>
date: <YYYY-MM-DD> · status: proposed | accepted | superseded by ADR-NNN · decided by: <user | seat>
from: ideation-NNN (if any)
## Context        the forces, briefly (link the ideation for the long form)
## Decision       what we do, stated so a reader can check compliance
## Consequences   what becomes easier, harder, and what we now must build or stop doing
## Alternatives   each rejected option and why
```

Number sequentially in `ops/adr/`, following the tree's existing numbering if it has one (`ADR-0006` after
`ADR-0005`); otherwise from `ADR-001`. Index it in `INDEX.md`. An accepted ADR is amended
only by a new ADR that supersedes it.

## Layout

Paths above follow the lab layout in `standards.docs`: `docs/` is the product as
it is, `ops/` is the working trail. If the tree's `AGENTS.md`/`CLAUDE.md` names
other homes, use those.
