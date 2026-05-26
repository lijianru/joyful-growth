# Architecture Research: Toddler Companion

## Component Boundaries

### Content Library

Stores learning items and activity templates:

- Item id
- Category: vocabulary, color, shape, number, expression
- Real photo asset
- Display label
- Spoken prompt
- Parent guidance
- Activity types supported

### Activity Engine

Turns content items into interaction flows:

- Picture selection
- Find-it prompt
- Repeat/respond prompt
- Gentle completion and wind-down

### Session Controller

Protects healthy-use constraints:

- Anytime exit
- 5-minute timer
- Wind-down state
- No infinite continuation

### Progress Store

Tracks simple parent-facing progress:

- Exposure count by item/category
- Recently played activities
- Category progress summaries
- Optional parent notes later

### Parent Dashboard

Shows:

- Today's short activity options
- Recent categories played
- Simple progress by vocabulary, colors, shapes, numbers, expressions
- Guidance that avoids pressure or performance framing

## Data Flow

1. Parent opens app.
2. App loads local content pack and local progress.
3. Parent/child chooses an activity.
4. Activity engine renders one prompt at a time.
5. Child taps or responds with parent guidance.
6. Session controller tracks time and provides wind-down.
7. Progress store records exposure/completion locally.
8. Parent dashboard reflects lightweight progress.

## Suggested Build Order

1. Mobile shell and content schema.
2. One activity type with real photos.
3. Session exit and wind-down.
4. Mixed activity engine.
5. Progress tracking.
6. Parent dashboard.
7. Content pack expansion and polish.

## Sources

- AAP: 5 Cs of Media Use — https://www.aap.org/5Cs
- AAP: Digital Screen Media and Cognitive Development — https://publications.aap.org/pediatrics/article/140/Supplement_2/S57/34173/Digital-Screen-Media-and-Cognitive-Development
- NAEYC: Technology and Young Children — https://www.naeyc.org/resources/topics/technology-and-media/
