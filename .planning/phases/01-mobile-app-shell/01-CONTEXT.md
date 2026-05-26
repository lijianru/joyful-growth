# Phase 1: Mobile App Shell - Context

**Gathered:** 2026-05-26T14:24:10.506Z
**Status:** Ready for planning

<domain>
## Phase Boundary

Phase 1 delivers the mobile Web app shell: a fast first screen, one fixed placeholder activity, a parent info sheet, and a weak record-entry empty state. It must prove the parent and child can open the app, start play in one or two taps, exit safely, and use the app without account setup or child data collection.

This phase does not deliver the full content pack, progress tracking, multiple activity types, configurable settings, or real session wind-down logic beyond visible shell affordances.

</domain>

<decisions>
## Implementation Decisions

### 首屏进入方式

- **D-01:** The home screen should emphasize direct play. `开始玩` is the primary action and should not be blocked by onboarding.
- **D-02:** The top bar should show the lightweight app name `小小认知`, but it must not compete with the main heading or primary action.
- **D-03:** Pressing `开始玩` enters one fixed placeholder activity, the "找苹果" demo.
- **D-04:** The `看看记录` entry remains visible but visually secondary; it opens an empty state until Phase 7 implements real progress.

### 占位活动真实程度

- **D-05:** The placeholder activity should use real-photo-style local sample images, not pure color blocks or illustrations.
- **D-06:** The demo includes three photo tiles: apple plus two everyday distractor objects.
- **D-07:** Example images should be stored in the repository as local replaceable assets. Do not depend on remote placeholder URLs.
- **D-08:** Demo feedback should be gentle. Tapping the apple may show warm feedback; tapping other items should avoid "wrong" language and can invite the child to look again.

### 家长说明出现时机

- **D-09:** Privacy and healthy-use guidance lives behind a top-bar information control, not an onboarding wall or persistent first-screen explanation.
- **D-10:** The parent info content should focus on two points: no baby information is uploaded, and each play session should stay short.
- **D-11:** The parent info surface should be a mobile bottom sheet.
- **D-12:** Do not include a settings entry in the parent info sheet during Phase 1.

### 记录入口表现

- **D-13:** `看看记录` opens an empty state sheet/page with `还没有记录` and the UI-SPEC body copy.
- **D-14:** Phase 1 should not write real progress data. The record surface is structural only.
- **D-15:** The empty record surface may reuse the same mobile sheet pattern as the parent info sheet.
- **D-16:** The empty state can offer `去玩一次`, returning to the fixed demo, but must not promise actual progress tracking before Phase 7.

### the agent's Discretion

The user explicitly approved defaulting subsequent discussion choices to recommended options after selecting the record empty state. The agent may choose conservative shell-level implementation details that preserve the locked UI-SPEC, avoid premature settings/progress features, and keep Phase 1 narrowly focused.

</decisions>

<canonical_refs>
## Canonical References

**Downstream agents MUST read these before planning or implementing.**

### Project Context

- `.planning/PROJECT.md` — Product vision, core value, constraints, and out-of-scope boundaries.
- `.planning/REQUIREMENTS.md` — v1 requirement IDs and Phase 1 traceability.
- `.planning/ROADMAP.md` — Phase 1 goal, requirements, and success criteria.
- `.planning/STATE.md` — Current workflow state and next-step context.

### Phase Design

- `.planning/phases/01-mobile-app-shell/01-UI-SPEC.md` — Locked UI design contract for copy, color, typography, spacing, screen contracts, and registry safety.

### Research

- `.planning/research/SUMMARY.md` — Product implications from AAP/WHO/NAEYC-informed research.
- `.planning/research/STACK.md` — Local-first mobile Web stack recommendation.
- `.planning/research/PITFALLS.md` — Anti-addiction, passive-screen-time, overstimulation, progress-pressure, and privacy pitfalls.

</canonical_refs>

<code_context>
## Existing Code Insights

### Reusable Assets

- No application code exists yet. Only planning artifacts and `AGENTS.md` are present.

### Established Patterns

- No existing app structure, component library, routing pattern, or styling system exists yet.
- Planning artifacts favor a local-first mobile Web approach and no third-party UI block registry for Phase 1.

### Integration Points

- Phase 1 must establish the initial app structure, asset location for local sample images, and reusable shell/sheet/tile patterns for later phases.

</code_context>

<specifics>
## Specific Ideas

- Home copy should follow UI-SPEC: app name `小小认知`, heading `今天玩一点点`, primary CTA `开始玩`, secondary CTA `看看记录`.
- Placeholder activity copy should follow UI-SPEC: `找一找：苹果在哪里？` and parent guidance `可以问宝宝：“你看到苹果了吗？”`.
- Parent info sheet should use UI-SPEC copy and emphasize privacy plus short use.
- Record empty state should use UI-SPEC copy: `还没有记录` and `玩过一次后，这里会显示最近探索过的内容。`

</specifics>

<deferred>
## Deferred Ideas

None — discussion stayed within phase scope.

</deferred>

---

*Phase: 1-Mobile App Shell*
*Context gathered: 2026-05-26T14:24:10.506Z*
