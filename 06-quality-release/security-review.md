# Security Review

<!-- This file tracks code-level security audit findings. -->
<!-- Run during Phase 6 (before QA sweep) or on-demand during Phase 5. -->
<!-- In Claude Code, use /security-review to run the audit. -->

**Status:** Not started
**Last reviewed:** —

---

## Review Summary

| Severity | Count | Fixed |
|----------|-------|-------|
| Critical |       |       |
| High     |       |       |
| Medium   |       |       |
| Low      |       |       |

---

## Findings

<!-- Findings are logged here by the security reviewer agent. -->
<!-- Format for each finding: -->

<!--
## Finding #1
**Severity:** Critical / High / Medium / Low
**Category:** Secrets | Auth | Injection | API | Data | Dependencies | Headers
**File:** path/to/file.ts:42
**Description:** What's wrong
**Exploit Scenario:** How an attacker could exploit this
**Fix:** Exact code change or configuration to apply
**Status:** Open / Fixed (commit hash)
-->

---

## Categories Reviewed

- [ ] Secrets & Environment Variables
- [ ] Authentication & Authorization
- [ ] Input Validation & Injection
- [ ] API Security
- [ ] Data Protection
- [ ] Dependencies (npm audit / equivalent)
- [ ] Headers & Configuration

---

## Dependency Audit

<!-- Paste output of npm audit (or equivalent) here -->

```
```

---

## Sign-Off

- [ ] All Critical findings fixed
- [ ] All High findings fixed
- [ ] Medium/Low findings fixed or accepted with reasoning
- [ ] Dependency audit clean (or accepted vulnerabilities documented)
- [ ] Ready for QA sweep
