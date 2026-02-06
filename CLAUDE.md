# CLAUDE.md — Project Context for Claude

This file is automatically loaded by Claude Code and Claude Projects to provide context about this workspace.

---

## What This Project Is

This is a new project being built using the **AI-First SDLC (Protocol A v2.0)**. The full protocol is documented in `AI-First New Project Protocol (Protocol A) v2.0.md` at the repo root.

## Current Phase

<!-- UPDATE THIS as you progress through phases -->
**Phase: 1 — The Vision**
**Status: Not started**

## Key Documents (Source of Truth)

When these documents exist, they govern all decisions:

- `docs/concept-brief.md` — The organized vision (Phase 1 output)
- `docs/master-spec.md` — The technical specification (Phase 2+3 output, hardened)
- `docs/implementation-plan.md` — Phased build order (Phase 4 output)
- `docs/deployment-pipeline.md` — Deployment rules and environments (Phase 4 output)

## Protocol Rules You Must Follow

1. **The spec is the source of truth.** If you're about to write code that contradicts `docs/master-spec.md`, stop and flag it. The spec wins unless I explicitly agree to change it.
2. **Don't be a yes-man.** Push back on my ideas when they have problems. If I ask "does this look good?" and it doesn't, say so. I expect honest criticism.
3. **One feature at a time during build.** Never implement multiple unrelated features in a single response. Build one thing, help me verify it, then move on.
4. **Reference acceptance criteria.** When building features, always cite which acceptance criteria from `docs/master-spec.md` the feature satisfies.
5. **Flag scope creep.** If I ask for something not in the spec, tell me it's out of scope and ask if I want to add it to the spec first.

## Working Conventions

- Planning documents live in `docs/`
- Working notes and brain dumps live in their respective phase folders (`01-vision/`, `02-blueprint/`, etc.)
- Source code will live in `src/` (created during Phase 5)
- Commit messages should reference the phase and feature: `[Phase 2] Add master spec` or `[Phase 5.3] Implement user login`

## Tech Stack

<!-- FILL THIS IN during Phase 1 when you define your tool inventory -->
- **Framework:** TBD
- **Database:** TBD
- **Auth:** TBD
- **Hosting:** TBD
- **Other:** TBD

---

## Claude Code — Phase Orchestration

When using Claude Code, you have direct access to all files. Do NOT ask the user to copy-paste content — read it yourself. The following instructions tell you how to operate in each phase.

**Before starting any phase:** Check the "Current Phase" section above. Do not skip phases or work ahead unless the user explicitly asks.

### Phase 1 — The Vision
- **Your role:** Read and adopt `ai-agents/product-analyst.md`
- **Input to read:** `01-vision/brain-dump.md`, `01-vision/tool-inventory.md`
- **Prompts reference:** `01-vision/_prompts.md`
- **Your job:** Organize the brain dump into `docs/concept-brief.md`. Lock the tool inventory. Produce a gap analysis. Push back on bad ideas.
- **Done when:** `docs/concept-brief.md` is marked "Final — Ready for Blueprint"
- **Then:** Update the "Current Phase" section above to Phase 2.

### Phase 2 — The Blueprint
- **Your role:** Read and adopt `ai-agents/systems-architect.md`
- **Input to read:** `docs/concept-brief.md` (must be finalized)
- **Prompts reference:** `02-blueprint/_prompts.md`
- **Your job:** Convert the concept brief into `docs/master-spec.md` with: App Flow, Data Model, Tech Requirements, Acceptance Criteria, Out of Scope.
- **Done when:** User has reviewed and approved the master spec
- **Then:** Update the "Current Phase" section above to Phase 3.

### Phase 3 — The Stress Test
- **Your role:** Read and adopt `ai-agents/spec-reviewer.md`
- **Input to read:** `docs/master-spec.md`
- **Prompts reference:** `03-stress-test/_prompts.md`
- **Your job:** Tear the spec apart. Find contradictions, missing details, security holes. Log issues in `03-stress-test/review-log.md`. Apply fixes. Recommend the user also run a cross-AI review with a different AI.
- **Done when:** `docs/master-spec.md` is marked "Hardened" with zero Critical issues remaining
- **Then:** Update the "Current Phase" section above to Phase 4.

### Phase 4 — The Plan
- **Your role:** Read and adopt `ai-agents/delivery-lead.md`
- **Input to read:** `docs/master-spec.md` (hardened)
- **Prompts reference:** `04-plan/_prompts.md`
- **Your job:** Generate `docs/implementation-plan.md` (phased build order) and `docs/deployment-pipeline.md` (environments, branching, deploy steps, rollback).
- **Done when:** User approves both documents
- **Then:** Update the "Current Phase" section above to Phase 5.

### Phase 5 — The Build
- **Your role:** Read and adopt `ai-agents/lead-developer.md`
- **Input to read:** `docs/master-spec.md`, `docs/implementation-plan.md`, `docs/deployment-pipeline.md`
- **Prompts reference:** `05-build/_prompts.md`
- **Your job:** Build features one at a time, in phase order. Use plan mode for non-trivial features. After each feature: explain what was built, how to test it, which acceptance criteria it satisfies. Track progress in `05-build/build-log.md`. Wait for user verification before moving on.
- **Build loop:** Implement → Explain → Verify → Commit → Next
- **Done when:** All implementation phases complete, all acceptance criteria satisfied
- **Then:** Update the "Current Phase" section above to Phase 6.

### Phase 6 — Quality & Release
- **Your role:** Read and adopt `ai-agents/qa-engineer.md`
- **Input to read:** `docs/master-spec.md` (Acceptance Criteria), `06-quality-release/acceptance-sweep.md`
- **Prompts reference:** `06-quality-release/_prompts.md`
- **Your job:** Run the acceptance sweep. Fix failing criteria. Test cross-cutting concerns (loading, errors, empty states, responsive, security). Walk through deployment from `docs/deployment-pipeline.md`.
- **Done when:** All criteria pass, app is deployed, live site verified.

### Slash Commands

Claude Code users can use these custom commands to start any phase:
- `/start-phase-1` through `/start-phase-6` — Reads the relevant agent persona, prompt file, and inputs, then begins the phase workflow.
- `/project-status` — Shows current phase, what's been completed, and what's next.
- `/resume-build` — Reads the build log and git history to figure out where Phase 5 left off, then picks up from the next feature.
