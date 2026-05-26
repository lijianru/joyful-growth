---
phase: 1
slug: mobile-app-shell
status: complete
created: 2026-05-26
sources:
  - https://react.dev/learn/creating-a-react-app
  - https://react.dev/learn/installation
  - https://vite.dev/guide/
  - https://vitest.dev/guide/learn/writing-tests.html
  - https://playwright.dev/docs/next/intro
---

# Phase 1 Research — Mobile App Shell

## Research Complete

Phase 1 should use the simplest credible mobile Web stack: React + Vite + TypeScript, with no backend, no account system, and no persistent child data. The phase is a shell and first interaction proof, not the content system or progress system.

## Stack Recommendation

### Framework

Use **React + Vite + TypeScript**.

Rationale:

- The React docs recommend using a framework for new apps, but also document build-tool setup such as Vite for cases where a full framework is not a good fit.
- This product is local-first, static, and does not need SSR, server components, auth, or backend routes in Phase 1.
- Vite officially supports `react-ts` templates and keeps the first scaffold small.

### Styling

Use plain CSS with centralized tokens in `src/styles/tokens.css` and `src/styles/app.css`.

Rationale:

- UI-SPEC explicitly says no component library for the v1 shell and semantic HTML controls first.
- Plain CSS avoids introducing Tailwind/shadcn configuration before there is any codebase pattern to justify it.
- CSS variables are enough for locked color, spacing, radius, and motion tokens.

### Data and Persistence

Do not add a database or child data persistence in Phase 1.

Rationale:

- Phase 1 requirements include no account setup and no child data collection.
- The record screen is an empty state only; real progress begins in Phase 7.
- If a future phase needs local persistence, use localStorage or IndexedDB then, not now.

### Sample Images

Use local repository assets under `public/demo/` for three real-photo-style sample images:

- `apple`
- `cup`
- `shoe`

Rationale:

- Context locks local assets over remote placeholder URLs.
- Local assets avoid network flakiness and keep the demo stable.
- The exact assets can be generated or curated during execution, but must be stored locally and referenced by the app.

## Validation Architecture

### Test Layers

1. **Type/build check:** `npm run build`
2. **Unit/component behavior:** Vitest + Testing Library for state transitions and text rendering.
3. **Browser behavior:** Playwright for mobile viewport checks, navigation, sheets, and no-account flow.

### Commands

- Quick: `npm run test -- --run`
- Full: `npm run build && npm run test -- --run && npm run test:e2e`

### What Must Be Verified

- Home renders `小小认知`, `今天玩一点点`, `开始玩`, and weak `看看记录`.
- Starting play opens the fixed `找一找：苹果在哪里？` demo.
- Demo has three local image tiles.
- Tapping apple gives warm feedback; tapping other items does not use harsh "wrong" copy.
- Parent info opens in a bottom sheet and states no baby info is uploaded plus short-use guidance.
- Record entry opens empty state without writing progress data.
- App works at 320px and 375px mobile widths without horizontal scroll.

## Risks and Mitigations

| Risk | Mitigation |
|------|------------|
| Shell grows into content/progress work | Keep Phase 1 to fixed demo, empty record state, and no data persistence. |
| Generic skeleton guidance pushes unnecessary DB | Explicitly document "no database in Phase 1" because privacy and scope prohibit child data writes. |
| UI becomes too game-like | Follow UI-SPEC: calm colors, no rewards, no streaks, no confetti, no loud effects. |
| Asset work blocks implementation | Use three small local sample images only; replace with structured content assets in Phase 2. |

## Planning Implications

- Plan 1 should scaffold app + home route/state.
- Plan 2 should implement fixed demo and bottom sheets.
- Plan 3 should add verification coverage and mobile checks.
- No plan should introduce accounts, analytics, backend APIs, cloud sync, microphone/camera access, or real progress storage.

## Sources

- React docs: Creating a React App — https://react.dev/learn/creating-a-react-app
- React docs: Installation — https://react.dev/learn/installation
- Vite docs: Getting Started — https://vite.dev/guide/
- Vitest docs: Writing Tests — https://vitest.dev/guide/learn/writing-tests.html
- Playwright docs: Installation — https://playwright.dev/docs/next/intro
