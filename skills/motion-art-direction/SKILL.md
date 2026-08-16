---
name: motion-art-direction
description: Design, implement, or refine intentional website motion systems. Use when work involves GSAP, ScrollTrigger, Lenis, Motion or Framer Motion, scroll choreography, page or section transitions, reveals, parallax, hover or cursor behavior, micro-interactions, animation performance, or reduced-motion alternatives.
---

# Motion art direction

Use motion to support hierarchy and storytelling. Give every animation a job: orient, reveal, connect, emphasize, acknowledge, or create atmosphere. Remove motion whose only rationale is that animation is possible.

## Workflow

### 1. Audit the experience

Inspect the content hierarchy, interaction states, current animation code, device constraints, and page performance. Identify narrative beats and moments where motion would clarify state or direct attention. Read [motion principles](references/motion-principles.md) before designing a broad system.

When working inside an isolated design prototype, scope motion code and dependencies to that prototype. Let competing prototypes explore different motion languages; do not force them through shared production animation architecture before selection.

### 2. Define the motion language

Write a short specification covering character, timing, easing, spatial logic, sequence, scroll relationship, and reduced-motion behavior. Inventory each proposed animation with its trigger, purpose, properties, duration, interruption behavior, and reduced-motion replacement. Delete inventory rows with no defensible purpose.

Use micro interactions around 120–250ms, UI transitions around 200–450ms, and major transitions around 500–1000ms as starting ranges, not rigid rules.

Choose dominant directions, depth behavior, masks, scale, or parallax. Define leads, followers, overlap, stagger, and rest moments. Use one coherent vocabulary across text, images, section transitions, navigation, cursor behavior, and hover states. Contrast a few hero moments with stillness.

### 3. Choose the smallest capable tool

- Use CSS transitions and keyframes for simple hover, focus, state, and decorative loops.
- Use Motion/Framer Motion when React lifecycle, presence, shared layout, or component state drives animation.
- Use GSAP when sequencing, precise timelines, masks, or complex transforms justify it. Read [GSAP](references/gsap.md).
- Use ScrollTrigger for coordinated reveals, scroll-linked timelines, or justified pinned sequences. Read [ScrollTrigger](references/scrolltrigger.md); avoid habitual pinning.
- Use Lenis only when smooth scrolling materially improves the concept and remains compatible with navigation and accessibility. Read [Lenis](references/lenis.md).
- Use Three.js/WebGL only when genuine 3D or shader-driven visuals carry the concept. A WebGL dependency is not a synonym for premium.

Read [micro-interactions](references/micro-interactions.md) for hover, cursor, magnetic, and feedback patterns.

Read [page transitions](references/page-transitions.md) when animation crosses routes or replaces whole-page content.

### 4. Implement safely

Animate `transform` and `opacity` where practical. Prevent flashes by establishing initial states before paint. Scope timelines, clean them up with component lifecycle, and avoid competing systems writing the same property. Keep focus, clicks, selection, anchors, back/forward navigation, and scrolling predictable.

Build `prefers-reduced-motion` behavior as a first-class variant. Read [reduced motion](references/reduced-motion.md). Do not merely set every duration to zero if that makes state changes confusing.

### 5. Tune in context

Run the page and inspect opening load, ordinary and rapid scrolling, reverse scrolling, navigation, hover, keyboard focus, resize, touch, and reduced-motion mode. Tune against real copy and media. Remove delays that block intent, parallax that separates content from its hit target, and motion that repeats until it becomes noise.

During prototype iteration, validate the affected animation and viewport rather than broad production suites. Run production-level regression and performance validation after the approved motion is integrated.

## Completion criteria

- Every animation has a named hierarchy, narrative, spatial, or feedback purpose.
- Timing, easing, direction, and sequencing share logic without becoming uniform.
- Input remains responsive and scroll behavior remains controllable.
- Mobile and reduced-motion variants preserve meaning with less movement.
- Animation code is scoped, cleaned up, and proportionate to the experience.
