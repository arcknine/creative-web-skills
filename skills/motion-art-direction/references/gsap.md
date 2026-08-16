# GSAP implementation

Use GSAP for timelines that need precise sequencing, reversible control, complex transforms, or coordinated masks. Keep simple state transitions in CSS.

## Structure

- Scope selectors to the component root with `gsap.context()` or framework-appropriate helpers.
- Create timelines after required nodes and fonts are ready.
- Set initial states explicitly to prevent flashes; ensure useful content remains visible if JavaScript fails.
- Kill timelines, triggers, observers, and listeners during teardown.
- Keep animation ownership clear. Do not let GSAP and CSS transitions write the same property concurrently.

```js
const ctx = gsap.context(() => {
  const tl = gsap.timeline({ defaults: { ease: "power3.out" } });
  tl.from("[data-title-line]", { yPercent: 110, stagger: 0.06, duration: 0.7 })
    .from("[data-hero-media]", { clipPath: "inset(0 0 100% 0)", duration: 0.9 }, "-=0.45");
}, root);

return () => ctx.revert();
```

Prefer semantic data attributes over styling-class selectors. Group defaults, label meaningful beats, and centralize shared easing values. Animate transforms rather than layout properties where possible. Measure frame behavior on target devices; a sophisticated timeline that drops frames is not premium.

Use `matchMedia()` or framework equivalents to author distinct narrow-screen and reduced-motion variants, not merely smaller distances.
