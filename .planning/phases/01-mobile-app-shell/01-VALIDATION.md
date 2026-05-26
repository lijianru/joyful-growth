---
phase: 1
slug: mobile-app-shell
status: approved
nyquist_compliant: true
wave_0_complete: false
created: 2026-05-26
---

# Phase 1 — Validation Strategy

> Per-phase validation contract for feedback sampling during execution.

---

## Test Infrastructure

| Property | Value |
|----------|-------|
| **Framework** | Vitest + Testing Library, Playwright |
| **Config file** | `vitest.config.ts`, `playwright.config.ts` |
| **Quick run command** | `npm run test -- --run` |
| **Full suite command** | `npm run build && npm run test -- --run && npm run test:e2e` |
| **Estimated runtime** | ~45 seconds after dependencies are installed |

---

## Sampling Rate

- **After every task commit:** Run `npm run test -- --run` once test infrastructure exists.
- **After every plan wave:** Run `npm run build && npm run test -- --run && npm run test:e2e`.
- **Before `$gsd-verify-work`:** Full suite must be green.
- **Max feedback latency:** 60 seconds.

---

## Per-Task Verification Map

| Task ID | Plan | Wave | Requirement | Threat Ref | Secure Behavior | Test Type | Automated Command | File Exists | Status |
|---------|------|------|-------------|------------|-----------------|-----------|-------------------|-------------|--------|
| 01-01-01 | 01-01 | 1 | SHELL-01 | T-01-01 | No account gate or child profile fields | build | `npm run build` | ❌ W0 | ⬜ pending |
| 01-01-02 | 01-01 | 1 | SHELL-02, SHELL-03, SHELL-04 | T-01-02 | Semantic buttons with mobile-safe layout | build | `npm run build` | ❌ W0 | ⬜ pending |
| 01-02-01 | 01-02 | 2 | SHELL-03, PRIV-01, PRIV-02 | T-01-03 | Local-only demo assets, no network data collection | unit/e2e | `npm run test -- --run && npm run test:e2e` | ❌ W0 | ⬜ pending |
| 01-02-02 | 01-02 | 2 | SHELL-02, SHELL-04 | T-01-04 | Sheets are dismissible and keyboard accessible | unit/e2e | `npm run test -- --run && npm run test:e2e` | ❌ W0 | ⬜ pending |
| 01-03-01 | 01-03 | 3 | SHELL-01, SHELL-02, SHELL-03, SHELL-04, PRIV-01, PRIV-02 | T-01-05 | Verification proves no account/analytics/child data forms | e2e/source | `npm run build && npm run test -- --run && npm run test:e2e` | ❌ W0 | ⬜ pending |

*Status: ⬜ pending · ✅ green · ❌ red · ⚠️ flaky*

---

## Wave 0 Requirements

- [ ] `package.json` — scripts for `build`, `test`, and `test:e2e`
- [ ] `vitest.config.ts` — jsdom test configuration
- [ ] `playwright.config.ts` — mobile viewport/browser configuration
- [ ] `src/App.test.tsx` — render and interaction tests
- [ ] `tests/mobile-shell.spec.ts` — e2e mobile shell checks

---

## Manual-Only Verifications

| Behavior | Requirement | Why Manual | Test Instructions |
|----------|-------------|------------|-------------------|
| Calm visual tone and toddler-friendly tap comfort | SHELL-02, SHELL-04 | Visual judgment still matters beyond automated viewport checks | Open the app at 375px width and confirm no cramped controls, no harsh game-like reward visuals, and no horizontal scroll. |

---

## Validation Sign-Off

- [x] All tasks have automated verify or Wave 0 dependencies.
- [x] Sampling continuity: no 3 consecutive tasks without automated verify.
- [x] Wave 0 covers all missing references.
- [x] No watch-mode flags in required verification commands.
- [x] Feedback latency target < 60s.
- [x] `nyquist_compliant: true` set in frontmatter.

**Approval:** approved 2026-05-26
