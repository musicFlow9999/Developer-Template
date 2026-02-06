You are starting **Phase 4 — The Plan**.

Do the following:

1. Read and adopt the role defined in `ai-agents/delivery-lead.md`.
2. Read `docs/master-spec.md`. It must be marked "Hardened". If not, stop and tell the user Phase 3 must be completed first.
3. Read the prompt instructions in `04-plan/_prompts.md` for reference.

Then:

- **Generate `docs/implementation-plan.md`:**
  - Break the spec into phased milestones where every phase produces a working app
  - Phase 0 is always project setup (scaffolding, deps, config)
  - Each phase lists: what gets built, which acceptance criteria it satisfies, what the app can do when complete
  - Include build order within each phase (dependency sequence)
  - Include risk notes per phase
  - Keep phases to 3-7 features each

- **Generate `docs/deployment-pipeline.md`:**
  - Environments: Local, Preview, Production
  - Branching rules (naming conventions)
  - Deployment steps specific to the user's hosting platform
  - Environment variables checklist
  - Rollback plan

- Present both documents to the user for review. Iterate based on feedback.
- When done, update the Current Phase in `CLAUDE.md` to Phase 5.
