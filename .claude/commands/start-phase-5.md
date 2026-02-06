You are starting **Phase 5 — The Build**.

Do the following:

1. Read and adopt the role defined in `ai-agents/lead-developer.md`.
2. Read `docs/master-spec.md`, `docs/implementation-plan.md`, and `docs/deployment-pipeline.md`. All three must exist. If any are missing, stop and tell the user which prerequisite phases need to be completed.
3. Read the prompt instructions in `05-build/_prompts.md` for reference.
4. Read `05-build/build-log.md` to see what's already been built (if resuming).

Then:

- Determine which implementation phase to start (or resume from the build log).
- **If starting Phase 0 (Project Setup):** After scaffolding the project, generate `docs/app-readme.md` with the app name, description, prerequisites, install commands, env var list, project structure, and tech stack. Pull content from `docs/concept-brief.md` and `docs/master-spec.md`.
- Use plan mode for non-trivial features before implementing.
- Follow the build loop strictly:
  1. **Implement** one feature at a time
  2. **Explain** what was built in plain English + which acceptance criteria it satisfies
  3. **Wait** for user verification — do NOT proceed until confirmed
  4. **Document** — Add an entry to `docs/changelog.md` (what was added/changed/fixed + technical notes for non-obvious decisions). Update `docs/app-readme.md` if the feature changes project structure, adds scripts, requires new env vars, or affects architecture.
  5. **Commit** with format `[Phase X.Y] Description` (only when user asks)
  6. **Log** progress in `05-build/build-log.md`
  7. **Next** feature

- Do NOT build ahead of verification.
- Do NOT introduce libraries/tools not in the spec without flagging it.
- Do NOT skip error handling, loading states, or empty states.
- Do NOT leave documentation for Phase 6 — update docs as you build.
- When all phases are complete, update the Current Phase in `CLAUDE.md` to Phase 6.
