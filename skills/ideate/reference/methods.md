# /ideate — Deep-Exploration Methods

<!-- DESIGN CONSTRAINT: capped at 5 techniques. If you want to add a sixth,
     first make the case that one of these should be removed. The point of
     this file is to stay short enough that the whole menu is legible at a
     glance; drift toward BMAD's 60-technique catalog is the failure mode. -->

A small, curated menu offered in Step 1 of `/ideate` when the problem benefits
from deeper interrogation before drafting. The user may pick one, or pick `[x]`
to skip and go straight to clarifying questions.

| Technique             | When to use                                                             | One-line prompt                                                              |
|-----------------------|-------------------------------------------------------------------------|------------------------------------------------------------------------------|
| Five Whys             | Symptom is visible but the root cause is unclear                        | "Ask 'why?' five times in sequence, each answer becoming the next subject."  |
| First Principles      | Solution space is crowded with inherited assumptions                    | "List what's actually true from the ground up; rebuild the problem from there." |
| Question Storming     | Problem feels fuzzy; user is reaching for a solution too fast           | "Generate ten questions the solution must answer; answer none of them yet."  |
| Assumption Reversal   | Proposed approach depends on a load-bearing belief                      | "Name the top 3 assumptions; for each, ask 'what if this is wrong?'"         |
| Pre-mortem            | Approach already feels obvious and the user is ready to commit         | "It's six months later and this failed. What killed it? What broke first?"   |

## How this plays in Step 1

1. Read the user's description.
2. If the description is short, vague, or the user asks for help exploring the problem, offer this menu with `[x] skip` as an option.
3. If the user picks a technique, apply it conversationally (one or two turns) before moving to Step 2.
4. If the user picks `[x]` or asks clarifying questions first, skip the menu and follow the original Step 1 path (up to 3 clarifying questions).
5. Do not offer the menu more than once per ideation session.
