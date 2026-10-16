---
name: design-spec-tldr
description: >-
  Distill AI-heavy PM feature specs (PRDs, tickets, acceptance criteria, goals,
  background) into a short designer-ready TL;DR: real goals, prioritized design
  tasks, out-of-scope, and open questions. Use when a designer pastes a feature
  write-up that feels like AI slop, asks what they should actually design, wants
  a design brief from a PRD, or says the spec is hard to parse.
icon: book-open
color: cyan
---

# Design Spec TL;DR

Turn a bloated, AI-assisted PM feature write-up into a **scannable designer brief**: what matters, what to design first, and what to ignore or clarify.

You are working **for the designer**, not rewriting the PRD for eng or PM.

## When to use

- Designer pastes a PRD / Feature Spec / Epic / ticket with goals, background, AC, success metrics, etc.
- They say it is hard to parse, full of fluff, or "AI slop"
- They ask: what should I design?, what's the real goal?, prioritize my design tasks

## Inputs

Accept any of:

1. Pasted spec text
2. A file / doc link / Notion / Confluence / ticket the user points at (fetch with available tools if needed)
3. A vague "help me figure out what to design from this"

If the input is missing or too thin to prioritize, ask for the full write-up once. Do not invent product context.

## Core job

1. **Strip slop** — ignore filler; keep decisions, constraints, and user outcomes
2. **Find the job** — one sentence: who, what changes, why it matters
3. **Translate to design work** — flows, surfaces, states, content, research — not eng tickets
4. **Prioritize** — P0 (blocks shipping a coherent experience) vs P1 vs later
5. **Surface gaps** — questions that would change the design if answered wrong

Load [references/slop-signals.md](references/slop-signals.md) when the document is long or obviously padded. Load [references/example.md](references/example.md) if you need a format calibration.

---

## Step 1 — Mine the signal

Read the whole input, then extract only:

| Bucket | Keep if… | Drop if… |
| --- | --- | --- |
| **User problem** | Concrete pain, job-to-be-done, or failure today | "Empower users", "delightful experiences", "leverage synergies" |
| **Outcome / goal** | Measurable or observable change in behavior | Vague vision paragraphs, mission restatements |
| **Scope** | Explicit in / out, MVP vs later | Repeated "phase 2" dreams with no owner |
| **Constraints** | Platform, brand, legal, timing, dependencies, existing patterns | Generic "best practices" lists |
| **Acceptance criteria** | Implies a screen, state, flow, or decision | Purely backend / analytics / infra with no UX surface |
| **Personas / journeys** | Distinct needs that change the UI | Persona theater ("Sarah, 34, loves efficiency") with no design implication |

**Designer translation rule:** If a requirement does not change what someone sees, taps, reads, or decides in the product, it is not a design task — mention it only under "Not your job" or ignore it.

---

## Step 2 — Infer design obligations

From the surviving signal, list concrete design work. Prefer verbs designers own:

- Map / clarify **flow** (happy path + critical branches)
- Define **IA / entry points** (where this lives, how users find it)
- Design **key screens / components** (name them)
- Specify **states** (empty, loading, error, success, permission, edge)
- Resolve **content & hierarchy** (what must be understood in 3 seconds)
- Call out **decisions** design must make or force with PM/eng
- Note **research / validation** only if the spec is ambiguous on user behavior

Do **not** expand into a full design system audit, visual exploration plan, or sprint ceremony unless the designer asks.

---

## Step 3 — Prioritize ruthlessly

Assign each design task:

- **P0 — Design now:** Required to ship a coherent MVP experience or unblock eng
- **P1 — Design next:** Important, but can follow the core flow
- **P2 — Later / nice:** Spec mentioned it; not needed for first useful version

If everything looks P0, you failed — force a cut. Prefer fewer P0 items (usually 3–7).

Also mark:

- **Blocked on answer:** Cannot responsibly design until PM/eng clarifies
- **Assumption:** You are inferring; state the assumption in one line

---

## Step 4 — Output format (always)

Keep the whole response short. Default to this structure and **nothing else** unless the designer asks for more:

```markdown
# Design TL;DR — [Feature name]

## In one sentence
[Who] can [do what] so that [outcome]. Ignore the rest of the vision deck.

## Real goals (design-relevant)
- …
- …

## Out of scope / not your job
- …
- …

## Prioritized design tasks
### P0 — Design now
1. **[Task]** — [why it matters / which AC or goal it serves]
2. …

### P1 — Design next
1. …

### P2 — Later
1. …

## Critical states & edges
- …

## Open questions for PM/eng
1. … (blocks: [which P0])
2. …

## Assumptions I'm making
- …
```

### Style rules for the output

- Plain language. Short bullets. No corporate adjectives.
- Do not mirror the spec's section order or headings.
- Do not paste large quotes from the spec.
- Do not invent metrics, personas, or requirements that are not implied.
- Do not produce wireframes, user stories, or eng tickets unless asked.
- If the spec is mostly noise, say so in one blunt line under the one-sentence summary, then still give the best brief you can.

### After the TL;DR — offer once (do not auto-run)

End the first response with **exactly one** short question (nothing else after it):

> Want a design statement from this?

- Do **not** generate the statement until they say yes (or ask for it).
- Ask **once** per TL;DR — if they ignore it or say no, move on.

---

## Optional follow-ups (only if asked)

### Design statement + rationale (default when they say yes)

If they accept the offer (or ask for a design statement), output **only** this — a JTBD design statement plus short work-shown. **Not** a full Focus wall by default.

Pull **only** from the TL;DR signal (one-sentence, Real goals, Out of scope, Prioritized tasks). Do not invent who, job, or outcome.

```markdown
## Design statement
As a [user] I want [capability] so that [outcome].

## How I got here
- **Who:** … (from Real goals / one-sentence)
- **Job:** … (the change that matters for design)
- **Outcome:** … (why it matters; what “done” looks like for the customer)
- **Scope cut:** … (what we left out so the statement stays shippable)
```

Keep **How I got here** to **3–5 bullets** so the statement feels earned, not mysterious.

### Full Focus exercise (only if asked)

Only if they explicitly want Focus scaffolding: users → pain → requirements → solutions → evaluation → statement. Most designers want the statement + work-shown above; do not expand into Focus unless requested.

### Other follow-ups

- Tighter checklist for a design critique
- Flow outline (steps only, still no UI)
- "Questions to send back to PM" as a paste-ready message
- Split by surface (mobile vs desktop) when the designer specifies platforms

## Anti-patterns

- Rewriting the PRD to be "better written" but still long
- Keeping every acceptance criterion as a design task
- Adding strategy theater (north stars, principles, opportunity statements)
- Auto-running a design statement or full Focus wall without being asked
- Inventing who/job/outcome not grounded in the TL;DR
- Turning this into a project plan with dates and staffing
- Softening ambiguity — if the spec contradicts itself, call it out in Open questions
