# Phase 1 Prompts — The Vision

Copy-paste these prompts into your conversational AI tool (Claude, ChatGPT, Gemini, etc.).

---

## Prompt 1: Organize the Brain Dump

> **Role:** Lead Product Analyst
>
> **Input:** Here is a raw brain dump of my app idea, including the tools and platforms I use:
>
> [PASTE CONTENTS OF `01-vision/brain-dump.md`]
>
> **Task:**
> 1. Organize my ideas without changing my core vision.
> 2. Lock my tool inventory — confirm the tools/platforms I have and flag any gaps (e.g., "You mentioned Supabase for database but didn't mention a hosting platform — do you have one?").
> 3. Output a file called `concept-brief.md` containing:
>    - **The One-Liner:** What is this app in one sentence?
>    - **The User:** Who uses it and why?
>    - **The Mechanics:** What does the app actually do, step by step?
>    - **The Tool Inventory:** Confirmed list of tools/platforms I'm working with.
>    - **The Gap Analysis:** 3–5 things I haven't thought through yet — risks, missing logic, unclear decisions.

---

## Prompt 2: The Reality Check

> **Input:** Here is the `concept-brief.md`:
>
> [PASTE CONCEPT BRIEF]
>
> **Input:** Here are my answers to the Gap Analysis:
>
> [PASTE YOUR ANSWERS]
>
> **Task:**
> 1. Update the brief with my answers.
> 2. **Stress Test:** Walk through the app as if you're a real user. Where does the experience break? Are we asking users to do something annoying, confusing, or unnecessary?
> 3. **Honest Assessment:** Tell me if any of my answers create new problems. Don't just agree with me — push back if something won't work.
> 4. Output the **final** `concept-brief.md`. Mark it "Final — Ready for Blueprint."

---

## Phase 1 Checklist

- [ ] Brain dump completed in `01-vision/brain-dump.md`
- [ ] Tool inventory filled in `01-vision/tool-inventory.md`
- [ ] Used Prompt 1 to generate draft concept brief
- [ ] Answered all Gap Analysis questions honestly
- [ ] Used Prompt 2 for reality check
- [ ] AI pushed back on at least one thing (if not, ask again harder)
- [ ] Final `concept-brief.md` saved to `docs/concept-brief.md`
- [ ] Concept brief marked "Final — Ready for Blueprint"
