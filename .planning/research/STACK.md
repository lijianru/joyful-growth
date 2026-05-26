# Stack Research: Toddler Companion

## Recommendation

Build v1 as a mobile-first static or lightweight React Web app with local-first data storage.

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

The project is explicitly mobile Web first and parent-guided. A local-first static app supports fast iteration, avoids privacy complexity around child data, and keeps the first release focused on interaction quality rather than infrastructure.

## Sources

- AAP: Media and Young Minds — https://publications.aap.org/pediatrics/article/138/5/e20162591/60503/Media-and-Young-Minds
- AAP: 5 Cs of Media Use — https://www.aap.org/5Cs
- WHO: Guidelines on physical activity, sedentary behaviour and sleep for children under 5 — https://www.who.int/publications/i/item/9789241550536
- NAEYC: Technology and Young Children, Infants and Toddlers — https://www.naeyc.org/resources/topics/technology-and-media/infants-and-toddlers
