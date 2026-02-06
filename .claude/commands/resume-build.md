You are resuming a build session that was interrupted. Your job is to figure out exactly where things left off and pick up seamlessly.

Do the following:

1. Read and adopt the role defined in `ai-agents/lead-developer.md`.
2. Read the Current Phase from `CLAUDE.md`. If it's not Phase 5, tell the user this command is for resuming mid-build and suggest the appropriate `/start-phase-X` command instead.
3. Read `docs/master-spec.md` for the full spec context.
4. Read `docs/implementation-plan.md` to understand the phase structure.
5. Read `05-build/build-log.md` to see what's been completed.
6. Run `git log --oneline -20` to see recent commits and match them against the build log.

Then present a concise status report:
- **Last completed feature:** What was the last thing built and verified
- **Current implementation phase:** Which phase of the implementation plan you're in
- **Next feature to build:** The specific next feature, with its acceptance criteria
- **Any loose ends:** Uncommitted changes, partially built features, or mismatches between the build log and git history

Wait for the user to confirm before starting work on the next feature. Follow the same build loop as `/start-phase-5`: one feature at a time, explain, verify, commit, next.
