<!-- GSD:project-start source:PROJECT.md -->

## Project

**Toddler Companion**

Toddler Companion is a mobile Web early-learning app for a 2-year-old child and parent to use together. The child interacts by tapping real-world photos while the parent guides nearby, with short activities around daily vocabulary, colors, shapes, numbers, and simple expressions.

The app is intentionally lightweight and can be exited at any time. It defaults to a gentle 5-minute wind-down and avoids addictive mechanics such as points, streaks, random rewards, or endless levels.

**Core Value:** Help a parent turn a few minutes of screen time into calm, guided language and cognition play that connects back to the real world.

### Constraints

- **Platform**: Mobile Web first — fastest path to trying the app on a phone without app store friction.
- **Audience**: 2-year-old child with parent guidance — controls must be large, forgiving, and simple.
- **Session design**: Anytime exit plus default 5-minute wind-down — protects attention and supports family routines.
- **Engagement ethics**: No addictive loops — avoid streaks, points, random rewards, endless levels, and pressure to continue.
- **Visual content**: Real photos preferred — supports recognition transfer to the physical world.
- **Progress tracking**: Simple parent-facing progress only — enough to show vocabulary/color/shape exposure without turning the app into performance pressure.

<!-- GSD:project-end -->

<!-- GSD:stack-start source:research/STACK.md -->

## Technology Stack

## Recommendation

## Suggested Stack

### App Foundation

- **React + Vite or Next.js static export**: Both are suitable for a fast mobile Web prototype. Vite is simpler for a local-first app; Next.js is useful if later adding accounts, server-side image optimization, or deployment conventions.
- **TypeScript**: Useful for keeping activity schemas, progress records, and content metadata reliable.
- **CSS Modules or Tailwind CSS**: Either works. The UI should remain calm, highly legible, and touch-friendly.

### Content Model

- **Static JSON content packs**: Define learning items with image path, labels, category, prompt text, accepted answers, and parent guidance.
- **Local image assets**: Use curated real photos for v1 to reduce dependency and privacy risk.
- **Progress in localStorage or IndexedDB**: Store simple exposure and completion counts locally for parent-visible progress without requiring login.

### Audio

- **Pre-recorded or browser speech synthesis only if quality is acceptable**: For a 2-year-old, audio clarity matters. Browser speech synthesis varies by device; pre-recorded parent-friendly audio can be higher quality but takes more production time.

### Deployment

- **Static hosting**: Vercel, Netlify, or similar static deployment is enough for v1.
- **No backend for v1**: Avoid user accounts, cloud child profiles, analytics, or remote media until the app proves useful.

## Rationale

## Sources

- AAP: Media and Young Minds — https://publications.aap.org/pediatrics/article/138/5/e20162591/60503/Media-and-Young-Minds
- AAP: 5 Cs of Media Use — https://www.aap.org/5Cs
- WHO: Guidelines on physical activity, sedentary behaviour and sleep for children under 5 — https://www.who.int/publications/i/item/9789241550536
- NAEYC: Technology and Young Children, Infants and Toddlers — https://www.naeyc.org/resources/topics/technology-and-media/infants-and-toddlers

<!-- GSD:stack-end -->

<!-- GSD:conventions-start source:CONVENTIONS.md -->

## Conventions

Conventions not yet established. Will populate as patterns emerge during development.
<!-- GSD:conventions-end -->

<!-- GSD:architecture-start source:ARCHITECTURE.md -->

## Architecture

Architecture not yet mapped. Follow existing patterns found in the codebase.
<!-- GSD:architecture-end -->

<!-- GSD:skills-start source:skills/ -->

## Project Skills

No project skills found. Add skills to any of: `.claude/skills/`, `.agents/skills/`, `.cursor/skills/`, `.github/skills/`, or `.codex/skills/` with a `SKILL.md` index file.
<!-- GSD:skills-end -->

<!-- GSD:workflow-start source:GSD defaults -->

## GSD Workflow Enforcement

Before using Edit, Write, or other file-changing tools, start work through a GSD command so planning artifacts and execution context stay in sync.

Use these entry points:

- `/gsd-quick` for small fixes, doc updates, and ad-hoc tasks
- `/gsd-debug` for investigation and bug fixing
- `/gsd-execute-phase` for planned phase work

Do not make direct repo edits outside a GSD workflow unless the user explicitly asks to bypass it.
<!-- GSD:workflow-end -->

<!-- GSD:profile-start -->

## Developer Profile

> Profile not yet configured. Run `/gsd-profile-user` to generate your developer profile.
> This section is managed by `generate-claude-profile` -- do not edit manually.
<!-- GSD:profile-end -->
