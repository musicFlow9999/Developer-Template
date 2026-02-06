# Phase 3 Prompts — The Stress Test

Use these prompts to have multiple AIs tear apart your spec. Use at **least two different AIs** (e.g., Claude + ChatGPT, or ChatGPT + Gemini).

**Prerequisite:** `docs/master-spec.md` exists from Phase 2.

---

## Prompt 1: Self-Review (Same AI that wrote the spec)

> **Input:** Here is the `master-spec.md`:
>
> [PASTE FULL SPEC]
>
> **Task:** You wrote this spec. Now **tear it apart.**
> 1. Read every section looking for: missing details, contradictions between sections, features described in the App Flow that aren't supported by the Data Model, and security holes.
> 2. Rank every issue by severity (Critical / Medium / Low).
> 3. For each issue, propose a specific fix — not just "this needs work" but the exact change to make.
> 4. Do NOT rubber-stamp it. If you say "looks great, no issues" I will assume you didn't actually review it.

---

## Prompt 2: Cross-AI Review (DIFFERENT AI)

> **Input:** I have a technical specification for an app I'm about to build. I need a critical review.
>
> Here is the `master-spec.md`:
>
> [PASTE FULL SPEC]
>
> **Task:** You did NOT write this spec. Review it as a hostile auditor.
> 1. Read every section looking for: missing details, contradictions between sections, features described in the App Flow that aren't supported by the Data Model, and security holes.
> 2. Rank every issue by severity (Critical / Medium / Low).
> 3. For each issue, propose a specific fix — not just "this needs work" but the exact change to make.
> 4. Be ruthless. I need to find every problem BEFORE I start building.

---

## Prompt 3: Apply Fixes

> **Input:** Here is the current `master-spec.md`:
>
> [PASTE FULL SPEC]
>
> **Input:** Here are the issues I've agreed to fix:
>
> [PASTE THE ISSUES YOU WANT FIXED FROM THE REVIEW LOG]
>
> **Task:**
> 1. Apply every fix to the spec.
> 2. For each fix, briefly explain what changed and why.
> 3. Output the complete updated `master-spec.md`.
> 4. Mark it "Hardened — Review Round [N] Complete" if this is the final round.

---

## When Are You Done?

Stop reviewing when:
- A review round returns **zero Critical** and only minor/cosmetic issues
- Typically takes **2–4 rounds**
- Issues flagged by multiple AIs are almost certainly real — prioritize those

---

## Phase 3 Checklist

- [ ] Round 1: Self-review completed (same AI as Phase 2)
- [ ] Round 1: Issues logged in `03-stress-test/review-log.md`
- [ ] Round 2: Cross-AI review completed (different AI)
- [ ] Round 2: Issues logged in review log
- [ ] Compared both reviews — dual-flagged issues prioritized
- [ ] All Critical issues fixed
- [ ] All Medium issues fixed or intentionally deferred with reasoning
- [ ] Additional review rounds until clean (if needed)
- [ ] `docs/master-spec.md` marked "Hardened"
- [ ] `03-stress-test/review-log.md` filled in with hardening summary
