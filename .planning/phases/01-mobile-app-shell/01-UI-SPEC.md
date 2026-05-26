---
phase: 1
slug: mobile-app-shell
status: approved
shadcn_initialized: false
preset: none
created: 2026-05-26
---

# Phase 1 - UI Design Contract

> Visual and interaction contract for the Toddler Companion mobile app shell. This phase creates the phone-first foundation for a calm parent-child early-learning experience.

---

## Phase Goal

Create a phone-friendly app foundation that opens quickly, needs no account, and is safe for parent-child use.

## Design Intent

The interface should feel calm, practical, and close to the real world. This is not a cartoon game lobby or a course dashboard. It is a small parent-child play surface: easy for a 2-year-old to tap, clear enough for a parent to guide, and gentle enough to stop without conflict.

Phase 1 does not need full learning content. It must establish the shell, navigation pattern, safety posture, and first placeholder activity entry so later phases can add real-photo content and interactions without redesigning the foundation.

---

## Design System

| Property | Value |
|----------|-------|
| Tool | none |
| Preset | not applicable |
| Component library | none for v1 shell; use semantic HTML controls first |
| Icon library | lucide-react if React is used; otherwise inline accessible SVG icons from the same stroke style |
| Font | system UI stack: `-apple-system, BlinkMacSystemFont, "Segoe UI", sans-serif` |
| Language | Simplified Chinese user-facing copy for parent/child flows |

### Component Principles

- Use native `button`, `main`, `nav`, `section`, and `dialog` semantics before custom widgets.
- Use icon + label buttons for parent controls; child-facing choices may be photo tiles with short labels.
- Keep cards to individual repeated items only, such as activity choices. Do not nest cards inside cards.
- Avoid decorative blobs, orbs, dark gradients, and marketing-style hero sections.
- Reserve images for actual learning/photo content, not decorative background.

---

## Layout Contract

### Viewports

| Viewport | Contract |
|----------|----------|
| 320-374px mobile | Single column, no horizontal scroll, photo/activity tiles remain tappable |
| 375-430px mobile | Primary target size for design decisions |
| 431-767px large phone | Same hierarchy with slightly larger spacing, no tablet-only layout |
| 768px+ tablet/desktop | Centered app canvas with max width 480px; no wide dashboard redesign in Phase 1 |

### App Shell

1. **Top bar**: compact parent-facing bar with app name and one settings/info control.
2. **Main area**: one primary activity starter section, then a small "recent/progress placeholder" area if needed.
3. **Bottom safe action**: persistent or near-bottom "休息一下" / exit affordance when inside an activity.
4. **No account gate**: first screen goes directly to play entry; any parent settings are optional and local.

### Touch Targets

- Child-facing primary tiles: minimum 88px by 88px.
- Parent controls: minimum 48px by 48px.
- Icon-only controls are allowed only with `aria-label`; visible labels are preferred.
- Minimum spacing between adjacent tap targets: 12px for child-facing choices, 8px for parent controls.
- Avoid horizontal swipe interactions in Phase 1.

---

## Spacing Scale

Declared values, all multiples of 4:

| Token | Value | Usage |
|-------|-------|-------|
| xs | 4px | Icon gaps, tiny alignment corrections |
| sm | 8px | Parent control gaps, compact labels |
| md | 16px | Default section and component spacing |
| lg | 24px | Screen padding, major group separation |
| xl | 32px | Between main screen groups |
| 2xl | 48px | First-screen vertical breathing room |
| 3xl | 64px | Tablet/desktop outer spacing only |

Exceptions: child-facing photo tiles may use internal padding based on image aspect ratio rather than fixed padding.

---

## Typography

| Role | Size | Weight | Line Height | Usage |
|------|------|--------|-------------|-------|
| Body | 16px | 400 | 1.5 | Parent guidance, body copy |
| Label | 14px | 600 | 1.35 | Button labels, tile captions |
| Heading | 22px | 700 | 1.25 | Screen heading |
| Display | 30px | 700 | 1.15 | Child prompt on activity screens |
| Helper | 13px | 500 | 1.45 | Low-priority parent notes |

Typography rules:

- Do not scale font size with viewport width.
- Letter spacing is 0.
- Child prompts should wrap naturally and never overlap controls or photo tiles.
- Avoid text smaller than 13px.
- Use Simplified Chinese copy with short phrases; do not rely on long instructions.

---

## Color

| Role | Value | Usage |
|------|-------|-------|
| Dominant (60%) | `#F7FAF8` | App background and quiet surfaces |
| Secondary (30%) | `#DDEEE7` | Activity tiles, gentle panels, selected calm states |
| Accent (10%) | `#2F7D7E` | Primary parent actions, focus ring, active nav state |
| Warm accent | `#E07A5F` | Rare positive feedback and wind-down cue only |
| Text strong | `#19302E` | Headings and primary labels |
| Text muted | `#5F6F6B` | Secondary copy |
| Border | `#C8D8D2` | Tile and panel boundaries |
| Destructive | `#B42318` | Destructive confirmations only |

Accent reserved for:

- Primary "开始玩" action.
- Current selected activity state.
- Keyboard focus ring.
- Parent settings confirmation.

Color rules:

- Do not use color alone to signal correctness or progress.
- Avoid full-screen gradients.
- Avoid high-saturation child-game palettes.
- Maintain WCAG AA contrast for parent-readable text.
- Child-facing photo tiles must have neutral borders and stable backgrounds so real photos remain the visual focus.

---

## Screen Contracts

### Home Screen

Purpose: let the parent and child start quickly.

Required elements:

- App name: `小小认知`
- Screen heading: `今天玩一点点`
- Primary CTA: `开始玩`
- Secondary action: `看看记录`
- Optional parent note: `不用登录，记录只保存在这台设备。`

Layout:

- App name in top bar, not a marketing hero.
- Heading and primary CTA visible without scrolling on 375px width.
- One primary CTA only. Secondary actions must be visually quieter.

### Placeholder Activity Screen

Purpose: prove the app shell can enter an activity before real content exists.

Required elements:

- Child prompt: `找一找：苹果在哪里？`
- 2-3 placeholder photo tiles using stable aspect-ratio boxes until content assets exist.
- Parent guidance line: `可以问宝宝：“你看到苹果了吗？”`
- Exit/wind-down action: `休息一下`

Layout:

- Prompt first, tiles second, parent guidance third.
- Photo tile grid: 2 columns on mobile; tiles keep a 1:1 aspect ratio.
- Exit action must remain visible or reachable without precision tapping.

### Parent Info Sheet

Purpose: explain privacy and healthy-use posture without blocking play.

Required elements:

- Heading: `给家长`
- Copy: `这个版本不需要账号，也不会上传宝宝信息。`
- Copy: `每次玩一小会儿，结束时可以回到真实物品和亲子互动。`
- Close action: `知道了`

Behavior:

- Opens from top bar info/settings control.
- Uses a modal sheet or full-screen sheet on mobile.
- Must close with button, Escape key, and backdrop click if a dialog pattern is used.

---

## Copywriting Contract

| Element | Copy |
|---------|------|
| App name | 小小认知 |
| Home heading | 今天玩一点点 |
| Primary CTA | 开始玩 |
| Secondary CTA | 看看记录 |
| Placeholder prompt | 找一找：苹果在哪里？ |
| Parent guidance | 可以问宝宝：“你看到苹果了吗？” |
| Wind-down action | 休息一下 |
| Empty progress heading | 还没有记录 |
| Empty progress body | 玩过一次后，这里会显示最近探索过的内容。 |
| Error state | 内容没有加载出来。请刷新页面再试一次。 |
| Destructive confirmation | 清除本机记录：只会删除这台设备上的记录，不能恢复。 |

Copy rules:

- Use warm, short, concrete Chinese.
- Avoid achievement pressure such as "mastered," "failed," "behind," or "score."
- Avoid engagement pressure such as "keep going," "do not miss today," or "streak."
- Avoid technical copy in child-facing areas.

---

## Interaction Contract

### Navigation

- Phase 1 has two core routes or states: home and placeholder activity.
- Parent info can be a sheet/modal state.
- Browser back should return from activity to home when routing exists.
- No bottom navigation in Phase 1 unless there are at least three stable destinations.

### Feedback

- Taps provide visible feedback within 100ms.
- Feedback is gentle: slight scale or background change, no confetti, no loud reward state.
- Disable controls only when an action is actively processing; otherwise keep the app forgiving.

### Motion

- Allowed: opacity and transform transitions, 150-220ms.
- Press feedback: scale to 0.98 for parent controls, 0.97 for child tiles.
- Respect `prefers-reduced-motion`.
- No bouncing, flashing, parallax, or continuous animation.

### Accessibility

- Use semantic buttons for all tappable actions.
- Every icon-only control needs `aria-label`.
- Focus indicators must be visible and use the accent color.
- Images need meaningful alt text when real assets are added.
- Do not disable pinch zoom.

---

## Registry Safety

| Registry | Blocks Used | Safety Gate |
|----------|-------------|-------------|
| shadcn official | none | not required |
| third-party registries | none | not allowed in Phase 1 without explicit review |

Registry rules:

- Do not introduce third-party UI block registries in Phase 1.
- If a component library is introduced later, prefer locally owned components for child-facing tiles and activity controls.

---

## Implementation Guardrails

- Use `min-height: 100dvh` or equivalent mobile-safe viewport handling.
- Reserve image tile dimensions with `aspect-ratio: 1 / 1`.
- Keep the shell local-first; do not add login, analytics, cloud sync, child profile forms, microphone access, or camera access.
- Use local placeholders for photos until the content pack phase.
- Keep CSS tokens centralized: colors, spacing, radius, shadows, motion.
- Border radius: 8px for panels and parent cards; photo tiles may use 12px only if it improves touch clarity.
- Avoid nested cards and decorative section cards.

---

## Checker Sign-Off

- [x] Dimension 1 Copywriting: PASS
- [x] Dimension 2 Visuals: PASS
- [x] Dimension 3 Color: PASS
- [x] Dimension 4 Typography: PASS
- [x] Dimension 5 Spacing: PASS
- [x] Dimension 6 Registry Safety: PASS

**Approval:** approved 2026-05-26
