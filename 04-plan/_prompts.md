# Phase 4 Prompts — The Plan

These prompts generate the implementation plan and deployment pipeline.

**Prerequisite:** `docs/master-spec.md` must be **hardened** (Phase 3 complete).

---

## Prompt 1: Generate Implementation Plan

> **Role:** Product Manager & Delivery Lead
>
> **Input:** The hardened `master-spec.md`:
>
> [PASTE FULL SPEC]
>
> **Task:** Break this spec into a phased build plan where **every phase produces a working app** that does more than the last.
>
> **Output:** A file called `implementation-plan.md` containing:
> 1. **Phases** — Logical groups of work (e.g., Phase 0: Project Setup, Phase 1: Database, Phase 2: User Login + Dashboard, etc.). Each phase should list:
>    - What gets built (specific files, features)
>    - Which acceptance criteria from the spec it satisfies
>    - What the app can do when this phase is complete
> 2. **Build Order** — The exact sequence within each phase. What depends on what.
> 3. **Risk Notes** — What could go wrong in each phase and how to handle it.

---

## Prompt 2: Generate Deployment Pipeline

> **Role:** DevOps Architect
>
> **Input:** `master-spec.md` (focus on Tech Stack and Security sections)
>
> **Input:** `implementation-plan.md` (focus on phases)
>
> [PASTE BOTH FILES]
>
> **Task:** Create the deployment strategy.
>
> **Output:** A file called `deployment-pipeline.md` containing:
> 1. **Environments** — The three places where the app exists:
>    - *Local:* Your computer. Only you can see it. For building and testing.
>    - *Preview:* A temporary website created automatically when you propose changes.
>    - *Production:* The real, live website your users see.
> 2. **Branching Rules** — How to name your work-in-progress versions (e.g., `feat/LOGIN-page`, `fix/DASHBOARD-error`).
> 3. **Deployment Steps** — Exactly how to connect your code repository to your hosting platform, step by step.
> 4. **Environment Variables** — A checklist of secret keys and URLs needed in each environment.
> 5. **Rollback Plan** — How to instantly revert if something goes wrong on the live site.

---

## How to Review the Implementation Plan

For each phase, ask yourself:
- Can I read "What the app can do when this phase is complete" and picture myself using it?
- Does each phase feel like a reasonable milestone?
- Does any phase feel too big? (If so, ask the AI to split it.)
- Does the build order make sense? (Does each phase build on the last?)

---

## Phase 4 Checklist

- [ ] `docs/master-spec.md` is hardened (Phase 3 signed off)
- [ ] Used Prompt 1 to generate implementation plan
- [ ] Each phase produces a usable milestone
- [ ] No phase is too large (max ~5-7 features per phase)
- [ ] Build order makes sense (dependencies flow correctly)
- [ ] `docs/implementation-plan.md` saved
- [ ] Used Prompt 2 to generate deployment pipeline
- [ ] Deployment steps are specific to your hosting platform
- [ ] Environment variables checklist is complete
- [ ] Rollback plan is documented
- [ ] `docs/deployment-pipeline.md` saved
- [ ] Ready for The Build (Phase 5)
