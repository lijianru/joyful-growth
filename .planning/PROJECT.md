# Toddler Companion

## What This Is

Toddler Companion is a mobile Web early-learning app for a 2-year-old child and parent to use together. The child interacts by tapping real-world photos while the parent guides nearby, with short activities around daily vocabulary, colors, shapes, numbers, and simple expressions.

The app is intentionally lightweight and can be exited at any time. It defaults to a gentle 5-minute wind-down and avoids addictive mechanics such as points, streaks, random rewards, or endless levels.

## Core Value

Help a parent turn a few minutes of screen time into calm, guided language and cognition play that connects back to the real world.

## Requirements

### Validated

(None yet — ship to validate)

### Active

- [ ] Provide mobile-first parent-child learning activities that a 2-year-old can tap through with parent guidance.
- [ ] Use real photos for everyday recognition, including a small but broad set of vocabulary, colors, shapes, numbers, and simple expressions.
- [ ] Support mixed interaction modes: picture selection, find-it prompts, and simple repeat/respond prompts.
- [ ] Allow sessions to end at any time and provide a gentle 5-minute wind-down by default.
- [ ] Avoid addictive engagement mechanics, including points, streaks, random rewards, infinite progression, and pressure to continue.
- [ ] Track simple progress across learning areas such as vocabulary, colors, and shapes for the parent.

### Out of Scope

- Native iOS or Android app — mobile Web is the first platform to validate the experience quickly.
- Long structured curriculum — v1 should feel like short parent-child play, not formal coursework.
- Child-only unsupervised mode — the intended experience is parent-guided use.
- Gamified rewards, streaks, leaderboards, or loot-style unlocks — these conflict with the anti-addiction goal.
- Video-heavy or highly stimulating media — the experience should stay calm and focused.

## Context

The user wants to build this for their 2-year-old child. The product should be practical for daily family use: quick to open on a phone, easy for a toddler to tap, and easy for a parent to guide without reading long instructions.

The desired content mix is "language recognition plus general early learning." Language and daily recognition are primary, with small amounts of colors, shapes, numbers, music or action prompts, and simple expressions. Real photos are preferred because they better connect the screen activity to objects and situations the child sees in everyday life.

The parent is part of the experience. The app should prompt or support the parent in guiding the child, but the child should still have the satisfying tactile action of tapping the screen.

## Constraints

- **Platform**: Mobile Web first — fastest path to trying the app on a phone without app store friction.
- **Audience**: 2-year-old child with parent guidance — controls must be large, forgiving, and simple.
- **Session design**: Anytime exit plus default 5-minute wind-down — protects attention and supports family routines.
- **Engagement ethics**: No addictive loops — avoid streaks, points, random rewards, endless levels, and pressure to continue.
- **Visual content**: Real photos preferred — supports recognition transfer to the physical world.
- **Progress tracking**: Simple parent-facing progress only — enough to show vocabulary/color/shape exposure without turning the app into performance pressure.

## Key Decisions

| Decision | Rationale | Outcome |
|----------|-----------|---------|
| Build mobile Web first | Fastest way to test on a phone and iterate without native app overhead | — Pending |
| Design for parent-child play | The parent should guide language input and keep screen use connected to real interaction | — Pending |
| Use real photos as primary content | Real photos are more directly useful for daily recognition than abstract illustrations | — Pending |
| Mix picture selection, find-it prompts, and repeat/respond prompts | Keeps v1 varied while staying simple enough for a toddler | — Pending |
| Default to a gentle 5-minute wind-down | Helps prevent extended screen sessions without abruptly blocking the child | — Pending |
| Exclude addictive mechanics | The product should support healthy use, not maximize engagement | — Pending |
| Include simple growth records | Parents need lightweight visibility into vocabulary, color, and shape exposure | — Pending |

## Evolution

This document evolves at phase transitions and milestone boundaries.

**After each phase transition** (via `$gsd-transition`):
1. Requirements invalidated? -> Move to Out of Scope with reason
2. Requirements validated? -> Move to Validated with phase reference
3. New requirements emerged? -> Add to Active
4. Decisions to log? -> Add to Key Decisions
5. "What This Is" still accurate? -> Update if drifted

**After each milestone** (via `$gsd-complete-milestone`):
1. Full review of all sections
2. Core Value check — still the right priority?
3. Audit Out of Scope — reasons still valid?
4. Update Context with current state

---
*Last updated: 2026-05-26 after initialization*
