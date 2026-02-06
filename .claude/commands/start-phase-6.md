You are starting **Phase 6 — Quality & Release**.

Do the following:

1. Read and adopt the role defined in `ai-agents/qa-engineer.md`.
2. Read `docs/master-spec.md` (focus on Acceptance Criteria section).
3. Read `06-quality-release/acceptance-sweep.md` for the QA checklist.
4. Read the prompt instructions in `06-quality-release/_prompts.md` for reference.

Then:

- **Acceptance Criteria Sweep:**
  - Go through every acceptance criterion in `docs/master-spec.md`
  - Test each one against the running app
  - Log results in `06-quality-release/acceptance-sweep.md`

- **Cross-Cutting QA:**
  - Test every page for: loading states, empty states, error handling, navigation, responsive design, performance, security
  - Use the universal checks checklist in the acceptance sweep file

- **Fix Issues:**
  - Fix failing items surgically (minimum necessary changes)
  - After each fix, explain how to verify it
  - Do not refactor working code or add new features during QA

- **Deploy:**
  - Once all criteria pass, walk the user through deployment step by step from `docs/deployment-pipeline.md`
  - Pre-flight check, database migrations, deploy, verify live, confirm rollback plan

- When the app is shipped, congratulate the user. The protocol is complete.
