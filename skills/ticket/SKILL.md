---
name: ticket
description: "Capture a defect or an idea as a ticket in ops/tickets/NNN_slug.md with a status."
---

# /ticket

```
---
status: open | fixed | closed | wontfix
kind: defect | idea | debt
found: <YYYY-MM-DD> · by: <seat | user>
fixed: <commit sha>   # when status: fixed
---
# NNN — <the root cause or the idea, in one line>
## Evidence   repro command, observed vs expected, file:line
## Class      the mechanism, so siblings can be swept
## Next       the smallest step that settles it
```

Number from 001 in `ops/tickets/`; index it in `INDEX.md`. Before filing, search the folder: a
rediscovery updates the old ticket. When a fix lands, set `status: fixed` and `fixed:` in the same change.

## Layout

Paths above follow the lab layout in `standards.docs`: `docs/` is the product as
it is, `ops/` is the working trail. If the tree's `AGENTS.md`/`CLAUDE.md` names
other homes, use those.
