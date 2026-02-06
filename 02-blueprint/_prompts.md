# Phase 2 Prompts — The Blueprint

Copy-paste these prompts into your conversational AI tool.

**Prerequisite:** `docs/concept-brief.md` must be marked "Final — Ready for Blueprint."

---

## Prompt 1: Generate the Master Spec

> **Role:** Systems Architect
>
> **Input:** The approved `concept-brief.md` (marked "Final"):
>
> [PASTE CONTENTS OF `docs/concept-brief.md`]
>
> **Task:** Convert this concept into a technical Master Specification that respects my Tool Inventory.
>
> **Output:** A file called `master-spec.md` containing:
> 1. **App Flow** — The complete user journey, screen by screen. (I should be able to read this section and "see" the app in my head.)
> 2. **Data Model** — What information the app stores and how it's organized. (Written as database code that developers/AI can execute directly.)
> 3. **Tech Requirements** — Security rules, speed expectations, design system (colors, fonts, spacing), and which tools handle what.
> 4. **Acceptance Criteria** — A checklist of testable statements: "The user can do X." "The screen shows Y." These define "done." (One checklist item per feature behavior, written so a non-technical person can verify by using the app.)
> 5. **Out of Scope** — Features we're intentionally *not* building yet, and which future phase they belong to.

---

## How to Review the Master Spec

Focus on these two sections:

### App Flow (Section 1)
Read it like a story. Ask yourself:
- Can I picture each screen?
- Does the flow match what I imagined?
- Is anything missing from the user journey?

### Acceptance Criteria (Section 4)
Read each item and ask:
- If I checked this box, would I be satisfied?
- Is anything missing that I'd want to verify?

If something doesn't match, tell the AI specifically what's wrong. Don't say "this doesn't feel right" — say "Step 3 shows the user going to a dashboard, but I imagined they'd go to a setup wizard first."

---

## Phase 2 Checklist

- [ ] Concept brief is finalized and marked "Final — Ready for Blueprint"
- [ ] Used Prompt 1 to generate master spec
- [ ] Reviewed App Flow section — it matches your vision
- [ ] Reviewed Acceptance Criteria — every box would satisfy you
- [ ] Reviewed Data Model — AI confirmed it supports all described features
- [ ] Flagged any mismatches or missing pieces to AI
- [ ] Final `master-spec.md` saved to `docs/master-spec.md`
- [ ] Ready for Stress Test (Phase 3)
