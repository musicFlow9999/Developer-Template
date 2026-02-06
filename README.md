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
│   ├── deployment-pipeline.md
│   ├── changelog.md                ← What changed per build phase + technical decisions
│   └── app-readme.md              ← Your app's README (setup, run, architecture)
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
│       ├── project-status.md      ← /project-status — check progress
│       └── resume-build.md       ← /resume-build — pick up where you left off
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
| `.claude/commands/` | Claude Code | Slash commands (`/start-phase-1` through `/start-phase-6`, `/project-status`, `/resume-build`) that auto-read agent personas and kick off each phase |
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
5. **Save your context.** If using a chat-based AI, always point it at `docs/master-spec.md` and `docs/implementation-plan.md` at the start of every session. (Claude Code does this automatically.)
6. **You make the decisions.** AI recommends. You approve.
7. **Done = checklist passes.** Not "looks done." Acceptance criteria checked = done.

---

## Getting Started Right Now

### Option A: Claude Code (Recommended)

Claude Code is the smoothest way to use this template. It reads all project files automatically — no copy-pasting prompts, no manually loading context. Here's how it works:

**Prerequisites:**
- [Claude Code](https://docs.anthropic.com/en/docs/claude-code) installed (`npm install -g @anthropic-ai/claude-code`)
- A repo created from this template

**First session — start your project:**

1. Open your terminal, `cd` into your project directory, and run `claude`
2. Claude Code automatically loads `CLAUDE.md`, which contains the full protocol rules and phase orchestration instructions. You don't need to tell it about the project — it already knows.
3. Fill in `01-vision/brain-dump.md` with your raw app idea (problem, audience, what it does, tools you use, inspiration). You can do this in your editor or ask Claude to help.
4. Type `/start-phase-1`

That's it. Claude reads your brain dump, adopts the Product Analyst persona, organizes your ideas into a concept brief, and walks you through gap analysis. When you approve the brief, it updates the project to Phase 2.

**Working through the phases:**

| Command | What Happens |
|---------|-------------|
| `/start-phase-1` | Reads brain dump, adopts Product Analyst role, produces `docs/concept-brief.md` |
| `/start-phase-2` | Reads concept brief, adopts Systems Architect role, produces `docs/master-spec.md` |
| `/start-phase-3` | Reads spec, adopts Hostile Reviewer role, tears it apart, produces hardened spec |
| `/start-phase-4` | Reads hardened spec, adopts Delivery Lead role, produces implementation plan + deployment pipeline |
| `/start-phase-5` | Reads all docs, adopts Lead Developer role, builds features one at a time |
| `/start-phase-6` | Reads spec + app, adopts QA Engineer role, runs acceptance sweep, walks you through deployment |

Each command checks prerequisites automatically. If you try to start Phase 3 before the spec exists, Claude will tell you to finish Phase 2 first.

**Utility commands:**

| Command | What It Does |
|---------|-------------|
| `/project-status` | Shows current phase, which documents are complete, and what to do next |
| `/resume-build` | For when you come back to a new session mid-Phase 5 — reads the build log and git history to figure out exactly where you left off |

**Coming back to a project:**

When you start a new Claude Code session (next day, new terminal, etc.):
- Claude automatically reloads `CLAUDE.md` with your current phase — no need to re-explain the project
- If you're mid-build, type `/resume-build` to pick up where you left off
- If you're between phases, type `/start-phase-X` for the next phase
- If you're not sure where you are, type `/project-status`

**What's happening under the hood:**

- `CLAUDE.md` auto-loads every session and tells Claude which phase you're in, which documents are the source of truth, and the five protocol rules it must follow
- Each `/start-phase-X` command reads the corresponding agent persona from `ai-agents/`, the prompt reference from the phase folder, and all relevant input documents
- Claude reads and writes files directly — it fills in templates, updates the build log, and modifies `CLAUDE.md` to track phase transitions
- You stay in control: Claude proposes, you approve. It won't move to the next feature or phase without your confirmation.

---

### Option B: Any Other AI (ChatGPT, Gemini, Copilot Chat, etc.)

If you're not using Claude Code, the template works with any AI through manual prompts:

1. Open `01-vision/brain-dump.md` and dump everything about your idea
2. Open `01-vision/_prompts.md` and copy-paste Prompt 1 into your AI tool
3. Optionally paste the agent persona from `ai-agents/product-analyst.md` as a system prompt for better results
4. Follow the phases in order, using each folder's `_prompts.md` for the prompts

**Tip:** At the start of every session, paste the contents of `docs/master-spec.md` and `docs/implementation-plan.md` so the AI has full context. Claude Code does this automatically, but with other tools you'll need to do it manually.

---

Good luck. Build something great.
