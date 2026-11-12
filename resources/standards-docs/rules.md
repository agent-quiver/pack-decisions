# Docs

One question decides where a document lives: **is it true of the product right now, and still useful if nobody
remembers how it got here?** Yes → `docs/`. It records deciding, planning, coordinating or investigating → `ops/`.

| `docs/` — the product as it is | `ops/` — the working trail |
|---|---|
| overview, getting started, guides | `ideation/`, `adr/`, `prd/`, `tickets/` |
| `architecture/` as built, glossary, context map | `handoffs/`, `mailbox/` |
| `operations/`: runbooks, deploy, backup, configuration | `research/`, `reports/`, `jumps/` |
| `reference/`, specs (or `spec/` at the root) | `migrations/` (registers), `media/` |
| | `state/` (the condensed summary and backlog agents read first: `standards.project-state`) |

**Product docs** (`README.md`, `CHANGELOG.md`, `CONTRIBUTING.md` at the root, and `docs/`):
- MUST describe what the product does, how to install, run and operate it, and the contracts it honours, with
  their versions;
- MUST be in the present tense, about behaviour and guarantees, with examples that run;
- MUST NOT hold roadmap musings, internal process, or the history of how a behaviour came to be (CHANGELOG lists
  *what* changed per version, plainly);
- MUST NOT link into `ops/`.
- Runbooks are product: they describe how it runs now, so they live in `docs/operations/`.
- Customer-facing material that must be published is a selection from `docs/`, or its own site repository; never
  from `ops/`.

**Specs** MUST be versioned (`vMAJOR.MINOR`) and normative (MUST/SHOULD), with a JSON Schema where the spec
defines a format, and a validator or conformance test that a third party can run.

**The working trail** (`ops/`) holds the reasoning: every document is dated and has a status, and every folder
has an `INDEX.md` that lists it, except `state/`, which holds two fixed files. Numbers are never reused. Nothing is left at the repository root.
