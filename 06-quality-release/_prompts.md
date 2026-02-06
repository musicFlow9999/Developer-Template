# Phase 6 Prompts — Quality & Release

**Prerequisite:** All build phases complete. App is running locally.

---

## Prompt 1: Fix Failing Acceptance Criteria

> **Context:** The build is complete. I'm doing the final quality check against `docs/master-spec.md`.
>
> **Input:** Here are the acceptance criteria that are **failing** (not working as expected):
>
> [PASTE FAILING ITEMS FROM `06-quality-release/acceptance-sweep.md`]
>
> **Task:**
> 1. For each failing item, investigate and fix it.
> 2. After fixing, tell me how to verify the fix.
> 3. When all fixes are applied, give me a final "ready to deploy" confirmation.

---

## Prompt 2: Cross-Cutting QA Fix

> **Context:** I ran the cross-cutting QA checklist (`06-quality-release/acceptance-sweep.md`) and found these issues:
>
> [PASTE FAILING UNIVERSAL CHECKS]
>
> **Task:**
> 1. Fix each issue.
> 2. These are app-wide concerns (loading states, error handling, empty states, etc.) — make sure fixes apply consistently across all pages.
> 3. Tell me which files were changed and how to verify each fix.

---

## Prompt 3: Finalize Documentation

> **Context:** All acceptance criteria pass. Before deploying, we need to finalize the project documentation.
>
> **Input:** Review these files:
> - `docs/changelog.md`
> - `docs/app-readme.md`
> - `docs/master-spec.md` (for Out of Scope → Known Limitations)
>
> **Task:**
> 1. Review `docs/changelog.md` — are all build phases logged? Are there placeholder entries that need filling in? Are Technical Notes captured for non-obvious implementation decisions?
> 2. Review `docs/app-readme.md` — does every section match the actual app? Are setup instructions accurate and complete? Are env vars listed? Is the project structure current? Are Available Scripts documented?
> 3. Fill in the Known Limitations section of `docs/app-readme.md` from the Out of Scope section of the master spec.
> 4. Fix anything that contradicts how the app actually works.
> 5. Output the finalized versions of both files.

---

## Prompt 4: Deploy to Production

> **Context:** All acceptance criteria pass. Ready to deploy.
>
> **Input:** Review `docs/deployment-pipeline.md`.
>
> **Task:** Walk me through the release process step by step.
> 1. **Pre-flight check:** Is all code committed? Any unsaved changes?
> 2. **Database:** If there are database changes (migrations), what needs to happen first?
> 3. **Deploy:** The exact steps to push to production.
> 4. **Verify live:** A checklist of things to test on the live site (not just locally).
> 5. **Rollback reminder:** How to instantly revert if something goes wrong on the live site.

---

## Phase 6 Checklist

- [ ] Acceptance sweep completed (`06-quality-release/acceptance-sweep.md`)
- [ ] All failing acceptance criteria fixed and re-verified
- [ ] Cross-cutting QA checklist passed (loading, errors, empty states, nav, responsive, perf, security)
- [ ] `docs/changelog.md` finalized — all phases logged, no placeholders, Technical Notes complete
- [ ] `docs/app-readme.md` finalized — setup instructions verified, all sections accurate
- [ ] All code committed with clean git status
- [ ] Database migrations applied (if any)
- [ ] Environment variables set in production
- [ ] Deployed to production following `docs/deployment-pipeline.md`
- [ ] Live site verified against acceptance criteria
- [ ] Rollback plan confirmed and understood
- [ ] 🎉 **SHIPPED**
