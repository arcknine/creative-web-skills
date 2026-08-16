# ScrollTrigger choreography

Use ScrollTrigger when scroll position meaningfully controls a narrative or coordinates elements that cannot be expressed cleanly with native CSS.

## Good uses

- Reveal related text and media as a composed beat.
- Scrub a transformation whose progress maps naturally to scrolling.
- Pin a bounded sequence while one stable context explains changing content.
- Coordinate a section handoff or controlled image mask.

## Guardrails

- Define explicit start/end logic and inspect markers during development.
- Refresh after fonts and media establish layout; avoid repeated layout reads in callbacks.
- Keep scrub distances proportional to the content. A short idea should not consume several viewports.
- Limit simultaneous pinned regions. Pinning changes the user's expected progress and can trap short screens.
- Avoid horizontal scroll hijacking unless the sequence genuinely requires it and has keyboard/touch alternatives.
- Toggle classes for simple state changes rather than driving every property through JavaScript.
- Kill triggers on teardown and after route changes.

Test slow, fast, and reverse scroll; direct anchor navigation; resized windows; mobile browser chrome; and content loaded late. A trigger must settle correctly when users enter mid-page. Replace pinned or scrubbed scenes with static readable compositions under reduced motion.
