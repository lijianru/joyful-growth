# Walking Skeleton — Toddler Companion

**Phase:** 1
**Generated:** 2026-05-26

## Capability Proven End-to-End

A parent can open the mobile Web app, see `小小认知`, tap `开始玩`, enter a fixed local-photo `找苹果` demo, receive gentle feedback, open parent/privacy guidance, and open an empty record state without account setup or child data collection.

## Architectural Decisions

| Decision | Choice | Rationale |
|---|---|---|
| Framework | React + Vite + TypeScript | Fits a local-first static mobile Web app without SSR, accounts, or backend routes. |
| Data layer | No database in Phase 1; local static assets and in-memory UI state only | Phase 1 must not collect child data or implement real progress tracking. The generic walking-skeleton DB requirement is intentionally narrowed by privacy/scope constraints. |
| Auth | None | Phase 1 explicitly requires no account setup. |
| Deployment target | Local dev server plus static build output | Fastest useful proof before choosing hosting. |
| Directory layout | `src/components`, `src/data`, `src/styles`, `public/demo`, `tests` | Small but structured enough for later content/activity phases. |

## Stack Touched in Phase 1

- [ ] Project scaffold (React, Vite, TypeScript, build, lint/test scripts)
- [ ] Routing/state — home, fixed demo, parent info sheet, record empty state
- [ ] Data — local static sample image metadata read by the app; no child data writes
- [ ] UI — one interactive demo wired to local component state
- [ ] Deployment — documented local full-stack static-app run command via `npm run dev` and production build via `npm run build`

## Out of Scope (Deferred to Later Slices)

- Real content pack beyond three sample demo images
- Progress tracking or localStorage writes
- Configurable session length
- Native iOS/Android app
- Accounts, cloud sync, analytics, microphone, camera, or child profile fields
- Multiple activity types beyond the fixed shell demo

## Subsequent Slice Plan

Each later phase adds one vertical slice on top of this skeleton without overturning these architectural decisions:

- Phase 2: Real-photo content pack and item schema
- Phase 3: Picture selection activity
- Phase 4: Find-it activity
- Phase 5: Repeat/respond activity
- Phase 6: Healthy session design
- Phase 7: Local progress
- Phase 8: Integration and launch polish
