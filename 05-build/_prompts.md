# Phase 5 Prompts — The Build

These prompts are for your **workspace-integrated AI tool** (GitHub Copilot, Claude Code, Cursor, etc.) — not a chat-only AI. The AI needs to read files, write code, and run commands.

**Prerequisite:** `docs/implementation-plan.md` and `docs/deployment-pipeline.md` exist from Phase 4.

---

## Prompt 1: Project Setup (Phase 0)

> **Role:** Senior Lead Developer
>
> **Context:** Review these project documents:
> - `docs/master-spec.md` — the hardened technical specification
> - `docs/implementation-plan.md` — the phased build plan (focus on Phase 0 / Project Setup)
>
> **Task:** Set up the project foundation.
> 1. Create the app using the framework from my spec.
> 2. Install all required tools and libraries listed in the spec.
> 3. Set up the design system (colors, fonts, spacing) from the spec's design tokens.
> 4. Set up the database connection and authentication.
> 5. Create the folder structure that matches the spec's project layout.
> 6. Generate `docs/app-readme.md` with: app name, description (from concept brief), prerequisites, install commands, environment variables list, project structure overview, and tech stack.
>
> Do this step by step. After each step, tell me what to verify before moving on.

---

## Prompt 2: Start a Build Phase

Use this at the beginning of each implementation phase:

> **Context:** We're starting **[Phase Name]** from the implementation plan.
>
> Review:
> - `docs/master-spec.md` — the technical specification
> - `docs/implementation-plan.md` — focus on the current phase
>
> **Task:**
> 1. List the features to build in this phase, in order.
> 2. Start with the first feature. Build it one at a time.
> 3. After each feature, tell me how to verify it and which acceptance criteria it covers.
> 4. Do NOT move to the next feature until I confirm the current one works.

---

## Prompt 3: Debug an Issue

> **Context:** I'm working on [FEATURE NAME] in [PHASE NAME].
>
> **What happened:**
> - I was trying to: [what you were doing]
> - I expected: [what should have happened]
> - Instead: [what actually happened]
> - Error message (if any): [paste it]
>
> **Task:** Diagnose and fix this issue. Explain what went wrong in plain English.

---

## Prompt 4: Commit Checkpoint

Use after each working feature:

> **Task:**
> 1. Summarize what was just built in one sentence.
> 2. Add an entry to `docs/changelog.md` under the current phase: what was added/changed/fixed, and a Technical Note if the implementation involved a non-obvious decision or trade-off.
> 3. If this feature added new scripts, env vars, changed the project structure, or affected the architecture, update `docs/app-readme.md` accordingly.
> 4. Give me the git commands to commit this work with a proper commit message following the format: `[Phase X.Y] Description`
> 5. Confirm: are there any uncommitted changes or temporary code that should be cleaned up first?

---

## The Build Loop (Reminder)

```
1. START PHASE → Tell AI which phase
2. BUILD FEATURE → AI creates/modifies code
3. VERIFY → Run app, check acceptance criteria
4. FIX (if broken) → Describe what happened, AI fixes
5. DOCUMENT → Update changelog + app README if needed
6. COMMIT → Save snapshot after each feature
7. NEXT FEATURE → Repeat until phase complete
8. NEXT PHASE → Repeat for next phase
```

**Rules:**
- One feature at a time
- Verify before moving on
- Commit after every working feature
- Always give the AI your spec context at session start

---

## Phase 5 Checklist

- [ ] Phase 0 (Project Setup) completed and committed
- [ ] `docs/app-readme.md` generated with setup instructions
- [ ] App runs locally with no errors
- [ ] Each implementation phase worked through in order
- [ ] Every feature verified against acceptance criteria
- [ ] `docs/changelog.md` updated after each feature
- [ ] `docs/app-readme.md` kept current (env vars, scripts, structure, architecture)
- [ ] Build log updated in `05-build/build-log.md`
- [ ] All phases committed with proper commit messages
- [ ] Ready for Quality & Release (Phase 6)
