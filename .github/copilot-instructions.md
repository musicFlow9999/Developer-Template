# GitHub Copilot Workspace Instructions

This project follows the **AI-First SDLC (Protocol A v3.0)**.

## Source of Truth

All code must align with these documents (in `docs/`):
- `docs/master-spec.md` — Technical specification (what to build)
- `docs/implementation-plan.md` — Build order (when to build it)
- `docs/deployment-pipeline.md` — Deployment rules (how to ship it)

If a document doesn't exist yet, the project is still in planning phases. Do not write production code until `docs/master-spec.md` exists and is marked "hardened."

## Build Rules

1. **One feature at a time.** Each PR should implement one feature from the implementation plan.
2. **Reference acceptance criteria.** Every feature must satisfy specific acceptance criteria from `docs/master-spec.md`. Cite them in PR descriptions and commit messages.
3. **Follow the spec's tech stack.** Do not introduce new dependencies or tools beyond what's specified in the master spec unless explicitly discussed.
4. **Flag contradictions.** If the code you're asked to write contradicts the spec, flag it rather than silently deviating.
5. **Commit messages format:** `[Phase X.Y] Description` (e.g., `[Phase 5.2] Implement user dashboard`)

## Code Style

<!-- UPDATE THIS during Phase 5 setup to match your project's conventions -->
- Follow the framework's official conventions
- Use the design system tokens defined in `docs/master-spec.md` (colors, fonts, spacing)
- Write descriptive variable/function names — clarity over brevity
- Include error handling and loading states for all async operations
- Add comments explaining "why" not "what"

## Project Structure

- `docs/` — Planning documents (source of truth)
- `src/` — Application source code
- `01-vision/` through `06-quality-release/` — Phase working folders (templates and notes)
- `ai-agents/` — AI agent personas for each protocol phase
