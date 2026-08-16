# Lenis decision guide

Add Lenis only when a continuous, weighted scroll feel is part of the motion concept or materially improves coordinated scroll scenes.

## Before adding it

Confirm that native scrolling cannot deliver the intended experience. Account for package weight, integration complexity, nested scrollers, modals, anchors, focus movement, browser history, touch input, and ScrollTrigger synchronization.

## Integration rules

- Maintain one animation frame loop and synchronize it deliberately with GSAP if both are present.
- Preserve anchor links, keyboard scrolling, focus-to-element behavior, and restoration after navigation.
- Stop scrolling only for a genuine modal state and always restore it.
- Exclude nested scroll regions intentionally rather than discovering conflicts later.
- Disable or bypass smoothing for reduced motion when the easing sensation itself is unwanted.
- Avoid extreme lerp/duration values that make input feel detached.

Test trackpad, mouse wheel, keyboard, touch, browser find, hash links, back/forward, and long pages. Remove Lenis if its contribution is not clearly perceptible or if it weakens control.
