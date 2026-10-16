# AI slop signals in PM feature specs

Use this when scanning a long write-up. Treat these as **low-signal by default** unless tied to a concrete user action or constraint.

## Phrases that usually mean nothing for design

- Empower / delight / seamless / intuitive / best-in-class / world-class
- Leverage / utilize / streamline / unlock / elevate / amplify
- Holistic / robust / scalable / flexible / end-to-end (with no boundary)
- "Drive engagement" / "increase efficiency" without a defined behavior change
- "Users want a modern experience"
- Restated company mission or product vision paragraphs

## Sections that are often padded

| Section | How to mine it |
| --- | --- |
| Background / Context | Keep only the current broken behavior or business trigger |
| Goals / Objectives | Keep outcomes that imply a UI or decision change; drop duplicates |
| Non-goals | High value — copy into Out of scope |
| Success metrics | Keep only if they imply what to optimize for in the UI (clarity, completion, time, errors) |
| Personas | Keep distinct needs; drop demographic fluff |
| Competitive landscape | Ignore unless it dictates parity requirements |
| Risks / Mitigations | Keep only UX or content risks |
| Future considerations / Phase 2 | Park in P2 unless labeled MVP |
| Acceptance criteria | Translate to screens/states/flows; drop pure API/data criteria |

## Structural smells

- Same idea repeated under Goals, Principles, and Success Criteria
- Numbered principles that do not conflict with anything (they never force a tradeoff)
- AC written as "system shall" with no actor and no interface
- Fake precision: five decimal places on a metric that has no baseline
- Exhaustive edge-case lists with no primary happy path

## What to elevate even if buried

- Explicit MVP cut line
- Legal / compliance / accessibility constraints
- Dependencies on other teams or existing patterns ("reuse checkout step 2")
- Contradictions (two mutually exclusive flows both marked must-have)
- Quotes from research or support tickets that describe real failure
