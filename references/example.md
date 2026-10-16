# Example — before / after

## Input (compressed AI-slop style)

> **Feature: Smart Save for later**
>
> Background: In today's fast-paced digital landscape, users struggle to manage
> content across sessions. By leveraging intelligent saving paradigms, we will
> empower members to curate a delightful, personalized library that unlocks
> long-term engagement and aligns with our north-star of seamless value creation.
>
> Goals: (1) Increase engagement. (2) Provide an intuitive save experience.
> (3) Build a scalable foundation for future collections. (4) Delight users.
>
> Success metrics: +15% D7 retention, +8% save rate, NPS impact TBD.
>
> Acceptance criteria:
> - User can save an item from the detail page
> - User can view saved items in a list
> - Saved state persists across sessions
> - Analytics events fire for save/unsave
> - Empty library shows educational content
> - Future: folders, AI recommendations, shareable collections
>
> Non-goals: Social sharing in v1. Offline sync in v1.

## Output (what the skill should produce)

```markdown
# Design TL;DR — Smart Save for later

## In one sentence
Members can save an item from detail view and find it again in a saved list so they can continue later — v1 is save/unsave + list, not collections.

## Real goals (design-relevant)
- Make "save for later" obvious on the item detail page
- Make returning to saved items easy and trustworthy (persisted state)
- Empty library should teach the habit, not feel broken

## Out of scope / not your job
- Analytics event wiring (eng)
- Folders, AI recommendations, shareable collections (explicitly later)
- Social sharing, offline sync (non-goals)
- Retention/NPS strategy theater — no design implication yet

## Prioritized design tasks
### P0 — Design now
1. **Detail-page save/unsave control** — entry point for the whole feature (AC: save from detail)
2. **Saved list (populated)** — primary return surface; hierarchy, item row, unsaved from list?
3. **Saved vs unsaved feedback** — clear state change so persistence feels real
4. **Empty saved list** — educational empty state (AC)

### P1 — Design next
1. **Navigation / entry to Saved** — where it lives in IA if not specified
2. **Unsave + undo or confirm** — destructive clarity if removing from list is easy

### P2 — Later
1. Folders / AI recommendations / shareable collections — explicitly future

## Critical states & edges
- First-time empty list
- Save success on detail
- Already saved (idempotent UI)
- Unsave from detail and from list
- Long list (scanability) — only if content volume is real

## Open questions for PM/eng
1. Where does Saved live in nav — new tab, profile, or overflow? (blocks P1 IA)
2. Can users unsave from the list in v1, or only from detail? (blocks list actions)
3. What is an "item" visually — thumbnail + title enough, or need price/meta? (blocks row design)

## Assumptions I'm making
- v1 is a flat list, not collections (matches non-goals / future section)
- Persistence is a trust cue in UI, not a separate settings surface
```
