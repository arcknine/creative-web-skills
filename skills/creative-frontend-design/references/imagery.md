# Imagery direction

Choose imagery for a defined role: hero, evidence, atmosphere, narrative sequence, texture, or subject portrait. A coherent crop and treatment can carry more identity than extra UI.

## Direct the frame

- Identify the subject, gaze, motion vector, and negative space. Place copy in naturally quiet areas instead of covering detail.
- Set focal-point-aware `object-position` values per breakpoint. A centered crop is rarely neutral.
- Use full bleed for immersion; use contained media when its objecthood, caption, or border matters.
- Use masks and clipping shapes that repeat the concept's shape language. One distinctive mask is stronger than many unrelated shapes.
- Layer transparent PNG/WebP/AVIF subjects over type or fields when silhouette and depth matter. Maintain clean edges and believable overlap.
- Build editorial collage from deliberate scale, crop, z-order, and shared alignment. Random rotation is not art direction.

## Responsive crops

Provide different aspect ratios or sources with `<picture>` when desktop and mobile need different frames. Never preserve a panoramic desktop crop if the mobile subject disappears. Reserve space with `width`/`height` or `aspect-ratio` to prevent layout shift.

## Video and depth

Use video when movement communicates material, place, performance, or atmosphere. Supply poster imagery, muted inline behavior where appropriate, playback controls for meaningful content, and a reduced-data/static alternative. Avoid autoplaying large media that delays the page's central message.

Create depth through occlusion, scale, focus, and motion hierarchy. Keep text readable and interactive layers unambiguous.

## Delivery

- Choose modern formats with sensible fallbacks and source dimensions.
- Generate responsive `srcset` sizes matching rendered slots.
- Load the likely LCP hero eagerly and with appropriate priority; lazy-load below-fold media.
- Compress to the perceptual needs of the crop and display density.
- Write useful alt text for informative images and empty alt text for decoration.
- Measure LCP, decode cost, and layout shift on representative mobile hardware.
