# 🚀 AI-First New Project Template

**A structured template for building apps using the AI-First SDLC (Protocol A v2.0).**

Use this repo as your starting point whenever you have a new app idea. It guides you through every phase — from raw brain dump to live deployment — with pre-written prompts, document templates, and AI configuration files that keep your AI assistants on track.

---

## How to Use This Template

### 1. Create a New Repo From This Template
Click **"Use this template"** on GitHub (or clone and reinitialize):
```
git clone <this-repo-url> my-new-project
cd my-new-project
rm -rf .git && git init
```

### 2. Follow the Phases in Order

| Phase | Folder | What You Do | Output |
|-------|--------|-------------|--------|
| **1. Vision** | `01-vision/` | Brain dump your idea, answer gap analysis | `docs/concept-brief.md` |
| **2. Blueprint** | `02-blueprint/` | Review the AI's technical translation | `docs/master-spec.md` |
| **3. Stress Test** | `03-stress-test/` | Multi-AI review, fix gaps | `docs/master-spec.md` (hardened) |
| **4. Plan** | `04-plan/` | Review build sequence & deployment rules | `docs/implementation-plan.md`, `docs/deployment-pipeline.md` |
| **5. Build** | `05-build/` | Verify each feature as AI builds it | Working app in `src/` |
| **6. Quality & Release** | `06-quality-release/` | Final acceptance sweep, deploy | Live app |

### 3. Use the Prompts
Each phase folder contains a `_prompts.md` file with **ready-to-use AI prompts** from the protocol. Copy-paste them into your AI tool of choice.

### 4. Finalized Docs Go in `docs/`
As you complete each phase, the output documents land in the `docs/` folder. These become the **single source of truth** for your project.

---

## Repo Structure

```
├── README.md                       ← You are here
├── CLAUDE.md                       ← Auto-loaded context for Claude Code / Claude Projects
├── .github/
│   └── copilot-instructions.md     ← Auto-loaded context for GitHub Copilot
├── .gitignore
│
├── docs/                           ← Finalized project documents (source of truth)
│   ├── concept-brief.md
│   ├── master-spec.md
│   ├── implementation-plan.md
│   └── deployment-pipeline.md
│
├── 01-vision/                      ← Phase 1: Brain dump + concept refinement
│   ├── brain-dump.md               ← YOUR raw ideas go here first
│   ├── tool-inventory.md           ← Your tools/platforms checklist
│   └── _prompts.md                 ← AI prompts for this phase
│
├── 02-blueprint/                   ← Phase 2: Technical specification
│   └── _prompts.md
│
├── 03-stress-test/                 ← Phase 3: Spec review & hardening
│   ├── review-log.md               ← Track issues found across review rounds
│   └── _prompts.md
│
├── 04-plan/                        ← Phase 4: Implementation plan + deployment
│   └── _prompts.md
│
├── 05-build/                       ← Phase 5: Feature-by-feature build
│   ├── build-log.md                ← Track what's built per phase
│   └── _prompts.md
│
├── 06-quality-release/             ← Phase 6: Final QA + ship it
│   ├── acceptance-sweep.md         ← Cross-cutting QA checklist
│   └── _prompts.md
│
├── ai-agents/                      ← Pre-configured AI agent personas
│   ├── product-analyst.md          ← Phase 1 agent
│   ├── systems-architect.md        ← Phase 2 agent
│   ├── spec-reviewer.md            ← Phase 3 agent
│   ├── delivery-lead.md            ← Phase 4 agent
│   ├── lead-developer.md           ← Phase 5 agent
│   └── qa-engineer.md              ← Phase 6 agent
│
├── .claude/                        ← Claude Code project configuration
│   ├── settings.json              ← Project-level settings
│   └── commands/                  ← Custom slash commands for phase transitions
│       ├── start-phase-1.md       ← /start-phase-1 — begin The Vision
│       ├── start-phase-2.md       ← /start-phase-2 — begin The Blueprint
│       ├── start-phase-3.md       ← /start-phase-3 — begin The Stress Test
│       ├── start-phase-4.md       ← /start-phase-4 — begin The Plan
│       ├── start-phase-5.md       ← /start-phase-5 — begin The Build
│       ├── start-phase-6.md       ← /start-phase-6 — begin Quality & Release
│       └── project-status.md      ← /project-status — check progress
│
├── src/                            ← Your app code goes here (created in Phase 5)
│   └── .gitkeep
│
└── AI-First New Project Protocol (Protocol A) v2.0.md  ← The full protocol reference
```

---

## AI Tool Configuration

This template includes configuration files for popular AI coding tools:

| File | Tool | What It Does |
|------|------|-------------|
| `CLAUDE.md` | Claude Code, Claude Projects | Gives Claude automatic context about your project, current phase, protocol rules, and phase orchestration instructions |
| `.claude/commands/` | Claude Code | Slash commands (`/start-phase-1` through `/start-phase-6`, `/project-status`) that auto-read agent personas and kick off each phase |
| `.claude/settings.json` | Claude Code | Project-level settings for Claude Code |
| `.github/copilot-instructions.md` | GitHub Copilot | Gives Copilot workspace-level context about your project and build standards |
| `ai-agents/` | Any AI tool | Pre-written agent personas (system prompts) for each phase — copy into any AI chat |

### Why Agent Personas?

The protocol assigns the AI a different **role** in each phase (Product Analyst → Systems Architect → Reviewer → etc.). The `ai-agents/` folder has these roles pre-written as standalone system prompts you can paste into any AI tool. This is more portable than tool-specific "skills" or "custom GPTs" because:

- They work with **any** AI (Claude, ChatGPT, Gemini, Copilot, Cursor, etc.)
- You can customize them per-project
- They're version-controlled with your project

---

## Process Rules (Non-Negotiable)

1. **The spec is the source of truth.** Code matches spec. If the spec is wrong, fix the spec first.
2. **Never skip the Stress Test.** Phase 3 saves more time than any other phase.
3. **Don't let AI be a yes-man.** Demand pushback. Ask "What's wrong with this?"
4. **One change at a time during build.** Build one feature, verify it, commit, move on.
5. **Save your context.** Always point AI at `docs/master-spec.md` and `docs/implementation-plan.md` at the start of every session.
6. **You make the decisions.** AI recommends. You approve.
7. **Done = checklist passes.** Not "looks done." Acceptance criteria checked = done.

---

## Getting Started Right Now

### Option A: Claude Code (Recommended)

1. Open your project in the terminal with Claude Code
2. Fill in `01-vision/brain-dump.md` with your app idea
3. Type `/start-phase-1` — Claude reads the brain dump, adopts the Product Analyst role, and walks you through the phase
4. When Phase 1 is done, type `/start-phase-2` and continue through the phases
5. Use `/project-status` at any time to see where you are

Claude Code reads all files directly — no copy-pasting needed. The `CLAUDE.md` file gives it full context about the protocol, and each slash command loads the right agent persona automatically.

### Option B: Any Other AI (ChatGPT, Gemini, Copilot Chat, etc.)

1. Open `01-vision/brain-dump.md` and dump everything about your idea
2. Open `01-vision/_prompts.md` and copy-paste Prompt 1 into your AI tool
3. Optionally paste the agent persona from `ai-agents/product-analyst.md` as a system prompt
4. Follow the phases in order, using each folder's `_prompts.md`

Good luck. Build something great.
