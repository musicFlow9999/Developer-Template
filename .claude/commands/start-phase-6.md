You are starting **Phase 6 — Quality & Release**.

Do the following:

1. Read and adopt the role defined in `ai-agents/qa-engineer.md`.
2. Read `docs/master-spec.md` (focus on Acceptance Criteria section).
3. Read `06-quality-release/acceptance-sweep.md` for the QA checklist.
4. Read the prompt instructions in `06-quality-release/_prompts.md` for reference.

Then:

- **Security Review (first):**
  - Read and adopt the role defined in `ai-agents/security-reviewer.md`.
  - Scan the `src/` directory systematically: secrets, auth/authz, injection, API security, data protection, dependencies (`npm audit` or equivalent), headers/config.
  - Log all findings in `06-quality-release/security-review.md`.
  - Fix all Critical and High findings before proceeding. Present Medium/Low findings for the user to accept or fix.
  - Security review must be signed off before continuing to the QA sweep.

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

- **Finalize Documentation:**
  - Read `docs/changelog.md` — verify all build phases are logged with no placeholder entries. Add any missing entries. Ensure Technical Notes capture non-obvious decisions.
  - Read `docs/app-readme.md` — verify every section is accurate and complete:
    - Setup instructions actually work (prerequisites, install, env vars, run commands)
    - Project structure matches the actual codebase
    - Available scripts are listed
    - Architecture overview reflects what was built
    - Known Limitations populated from `docs/master-spec.md` Out of Scope section
  - Fix any documentation that contradicts the actual app behavior.

- **Deploy:**
  - Once all criteria pass and documentation is finalized, walk the user through deployment step by step from `docs/deployment-pipeline.md`
  - Pre-flight check, database migrations, deploy, verify live, confirm rollback plan

- When the app is shipped, congratulate the user. The protocol is complete.
