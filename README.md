# Decisions pack

`agent-quiver/pack-decisions` is an open [Quiver pack](https://github.com/agent-quiver/pack-standard).

Skills for the paper trail of a project: ideate (explore a problem before deciding), adr (record a hard-to-reverse decision), prd (plan a change as stories with acceptance), ticket (one unit of work), and the docs rulebook that says where each document lives.

## Use it

- **As files:** clone it, or add it to a repository as a git submodule at a release tag. `skills/` follows the Agent Skills layout.
- **Through Quiver:** add the pack to your quiver and connect your agent (coming with the first Quiver release that serves packs).
- **Change it:** open a pull request. A release is a tag `vX.Y.Z`; see `CHANGELOG.md`.

## Artifacts

| kind | id | version | when to use |
|---|---|---|---|
| skills | `ideate` | 2.1.1 | A problem worth exploring before deciding: forces, options, evidence, a recommendation in ops/ideation/. |
| skills | `adr` | 2.1.2 | A hard-to-reverse decision was made: record context, decision, consequences and alternatives in ops/adr/. |
| skills | `prd` | 1.1.3 | A decided change needs a plan: user stories with acceptance criteria and gates in ops/prd/. |
| skills | `ticket` | 2.1.1 | A defect or idea to capture for later: one file in ops/tickets/ with a status. |
| resources | `standards.docs` | 1.2.0 | Deciding where a document lives: docs/ for the product as it is, ops/ for the working trail. |

## Licence

Text in this pack is licensed under CC-BY-4.0 (`LICENSE`).
