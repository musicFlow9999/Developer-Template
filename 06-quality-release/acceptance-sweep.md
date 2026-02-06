# Acceptance Sweep — Cross-Cutting QA Checklist

Run this checklist against **every page / feature** of your app before release.

---

## Universal Checks (Every Page)

### Loading States
- [ ] When data is loading, user sees a placeholder (skeleton, spinner) — not a blank screen
- [ ] Loading states appear within 200ms of initiating an action
- [ ] Long operations (>2s) show progress indication

### Empty States
- [ ] When there's no data yet, the page explains what to do next
- [ ] Empty states have a clear call-to-action (e.g., "Create your first ___")
- [ ] Empty states don't show broken layouts or undefined values

### Error Handling
- [ ] When something fails (bad connection, server error), user sees a helpful message
- [ ] Error messages include a way to retry or go back
- [ ] Form validation shows inline errors — not just a generic "something went wrong"
- [ ] No unhandled errors in browser console during normal use

### Navigation
- [ ] User can always get back to where they started (no dead ends)
- [ ] Browser back button works as expected
- [ ] All navigation links/buttons lead somewhere (no broken links)
- [ ] Current page/section is clearly indicated in navigation

### Responsive Design
- [ ] App looks reasonable on mobile (320px width)
- [ ] App looks reasonable on tablet (768px width)
- [ ] No horizontal scrolling on any device
- [ ] Touch targets are at least 44x44px on mobile
- [ ] Text is readable without zooming

### Performance
- [ ] Pages load in under 3 seconds on a normal connection
- [ ] No visible jank or layout shift during load
- [ ] Images are appropriately sized (not loading 4000px images for thumbnails)

### Security
- [ ] Authenticated routes redirect to login when not logged in
- [ ] Users cannot access other users' data by changing URLs
- [ ] Sensitive data (API keys, tokens) is not exposed in client-side code
- [ ] Forms are protected against double-submission

---

## Feature-Specific Acceptance Criteria

<!-- Copy acceptance criteria from docs/master-spec.md and check each one -->

| # | Criteria | Tested | Pass? | Notes |
|---|----------|--------|-------|-------|
| 1 |          | ☐      | ☐     |       |
| 2 |          | ☐      | ☐     |       |
| 3 |          | ☐      | ☐     |       |
| 4 |          | ☐      | ☐     |       |
| 5 |          | ☐      | ☐     |       |

---

## Failing Items

<!-- List any items that failed above — these get sent to the AI for fixing -->

1.
2.
3.
