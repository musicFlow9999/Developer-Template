You are starting **Phase 2 — The Blueprint**.

Do the following:

1. Read and adopt the role defined in `ai-agents/systems-architect.md`.
2. Read the finalized concept brief from `docs/concept-brief.md`. If it is not marked "Final — Ready for Blueprint", stop and tell the user Phase 1 must be completed first.
3. Read the prompt instructions in `02-blueprint/_prompts.md` for reference.

Then:

- Convert the concept brief into `docs/master-spec.md` with these sections:
  1. **App Flow** — Complete user journey, screen by screen (readable as a story)
  2. **Data Model** — Executable database schema (SQL or equivalent)
  3. **Tech Requirements** — Security, performance, design system, tool assignments
  4. **Acceptance Criteria** — Testable checklist ("The user can do X", "The screen shows Y")
  5. **Out of Scope** — What we're NOT building yet
- Respect the user's tool inventory from the concept brief. Do not swap tools without flagging it.
- Present the spec to the user for review. Focus their attention on App Flow and Acceptance Criteria.
- Iterate based on feedback until the user approves.
- When done, update the Current Phase in `CLAUDE.md` to Phase 3.
