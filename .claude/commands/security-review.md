You are performing a **security review** of the codebase.

This command can be run at any time — during Phase 5 (mid-build) or Phase 6 (pre-release). It does not require a specific phase to be active.

Do the following:

1. Read and adopt the role defined in `ai-agents/security-reviewer.md`.
2. Read `docs/master-spec.md` (focus on security rules and auth requirements in Tech Requirements).
3. Read `06-quality-release/security-review.md` to see if any previous reviews have been done.
4. Scan the `src/` directory to understand the project structure.

Then systematically review the codebase in this order:

1. **Secrets & Environment Variables** — Scan all source files for hardcoded secrets. Verify `.gitignore` covers env files. Check client-side bundles don't expose secrets.
2. **Authentication & Authorization** — Verify every protected route checks auth. Test for broken access control. Check session/token handling.
3. **Input Validation & Injection** — Check for SQL injection, XSS, command injection, path traversal. Verify all user input is validated.
4. **API Security** — Check request validation, rate limiting, CORS config, error response leakage.
5. **Data Protection** — Check for sensitive data in logs, over-fetching from database, encryption in transit.
6. **Dependencies** — Run `npm audit` (or equivalent) and flag known vulnerabilities.
7. **Headers & Configuration** — Check security headers, cookie flags, production config.

Log all findings in `06-quality-release/security-review.md` using the format defined in the agent persona.

Present a summary to the user:
- Total findings by severity (Critical / High / Medium / Low)
- Top priority items to fix immediately
- For each finding, the exact fix to apply

If Critical or High findings exist, recommend fixing them before proceeding with deployment. Offer to apply the fixes.
