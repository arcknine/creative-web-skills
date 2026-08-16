# Typography as composition

Use type to establish identity and spatial order before adding decoration.

## Assign roles

- Choose a display face for personality and a utility face for sustained reading. One variable family can perform both roles if its axes create real contrast.
- Pair by productive tension: condensed display with neutral grotesk, expressive serif with disciplined sans, or wide geometric display with compact utility text. Avoid two faces with nearly identical character.
- Do not default to Inter or the framework starter font. Inspect brand, language coverage, licensing, loading cost, numerals, punctuation, and available weights first.
- Limit the active palette of faces and weights. Distinction should come from scale, width, case, rhythm, and placement—not a font sampler.

## Build contrast

Define a small hierarchy with visibly different jobs: display, section title, deck, body, label, metadata. Adjacent levels must differ enough to scan at a glance. A timid ratio produces a uniformly gray page.

Use fluid sizes when the composition benefits:

```css
--step-display: clamp(3.5rem, 2rem + 7vw, 10rem);
--step-title: clamp(2rem, 1.3rem + 3vw, 5rem);
--step-body: clamp(1rem, 0.96rem + 0.2vw, 1.125rem);
```

Tune each clamp from a chosen minimum and maximum viewport; do not scatter arbitrary formulas. Test zoom and long translations.

## Shape the text block

- Tighten display line-height until lines lock together without collisions; body text generally needs more air.
- Control measure: roughly 45–75 characters is a useful body-text starting range, not a universal law.
- Use deliberate line breaks when they strengthen a headline composition. Remove them or provide breakpoint-specific breaks before they create stranded words.
- Balance letter-spacing with face and size. Uppercase utility labels often need tracking; large display type often needs less.
- Align cap heights, baselines, and text edges with media or grid lines—not just bounding boxes.

## Make type structural

Let headlines span columns, crop at viewport edges, wrap around media, become masks, or establish the page's dominant axis. Kinetic type should reveal reading order or physical character; splitting every heading into animated words is not a concept.

On mobile, recompose rather than proportionally reduce. Change line breaks, width, alignment, and relationship to imagery. Protect readable body sizes and touch labels while allowing display type to remain bold.
