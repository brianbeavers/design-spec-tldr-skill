# Design Spec TL;DR

A portable **Cursor Agent Skill** that turns bloated, AI-assisted PM feature write-ups (PRDs, tickets, acceptance criteria, goals, background) into a short **designer-ready** brief: real goals, prioritized design tasks, out-of-scope, and open questions.

Built for designers who need to know what to design — not a PRD rewrite for eng or PM.

## Quick start

```bash
mkdir -p ~/.cursor/skills
git clone https://github.com/brianbeavers/design-spec-tldr-skill.git ~/.cursor/skills/design-spec-tldr
```

In Cursor Agent chat, paste a spec and say:

```text
/design-spec-tldr

[paste PRD / feature spec / ticket]
```

Or copy this folder into a project as `.cursor/skills/design-spec-tldr/`.

## What it does

1. **Strips slop** — keeps decisions, constraints, and user outcomes
2. **Finds the job** — one sentence: who, what changes, why it matters
3. **Translates to design work** — flows, surfaces, states, content — not eng tickets
4. **Prioritizes** — P0 vs P1 vs later
5. **Surfaces gaps** — questions that would change the design if answered wrong

## Repo layout

| Path | Role |
| --- | --- |
| [`SKILL.md`](SKILL.md) | Skill instructions (agent loads this) |
| [`references/slop-signals.md`](references/slop-signals.md) | Common AI-padding patterns to ignore |
| [`references/example.md`](references/example.md) | Before/after format calibration |

## Output shape

A scannable markdown TL;DR: one-sentence job, real goals, design tasks by priority, out of scope / not your job, and open questions.

## License

MIT — see [LICENSE](LICENSE).
