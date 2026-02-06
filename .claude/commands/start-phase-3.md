You are starting **Phase 3 — The Stress Test**.

Do the following:

1. Read and adopt the role defined in `ai-agents/spec-reviewer.md`.
2. Read `docs/master-spec.md`. If it does not exist or is empty, stop and tell the user Phase 2 must be completed first.
3. Read the prompt instructions in `03-stress-test/_prompts.md` for reference.
4. Read `03-stress-test/review-log.md` to understand the tracking format.

Then:

- **Round 1 — Self-Review:** Tear the spec apart as a hostile auditor. Look for:
  - Contradictions between App Flow and Data Model
  - Features with no acceptance criteria
  - Missing error states, empty states, edge cases
  - Security holes (auth bypasses, data leaks, missing validation)
  - Data model entities not referenced by any feature (orphans)
- Rank every issue by severity (Critical / Medium / Low).
- For each issue, propose a **specific** fix — not "this needs work" but the exact change.
- Log all findings in `03-stress-test/review-log.md` under Round 1.
- Present the findings to the user. Apply agreed fixes to `docs/master-spec.md`.
- **Recommend Cross-AI Review:** Tell the user to also run the Cross-AI Review prompt from `03-stress-test/_prompts.md` (Prompt 2) in a different AI tool for a second opinion. If they bring back findings, apply those fixes too and log them as Round 2.
- Continue review rounds until zero Critical issues remain.
- Mark `docs/master-spec.md` as "Hardened" and fill in the hardening summary in the review log.
- When done, update the Current Phase in `CLAUDE.md` to Phase 4.
