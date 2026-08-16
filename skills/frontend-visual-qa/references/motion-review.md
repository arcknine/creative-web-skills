# Motion review

Review motion at normal use speed and under stress. A still screenshot cannot prove a motion system.

## Inspect the sequence

Test initial load, first interaction, ordinary and fast scroll, reverse scroll, repeated entry, route change, resize, touch, and reduced motion. For each animation ask:

- What hierarchy, orientation, continuity, feedback, or atmosphere does it provide?
- Does it begin from and settle into a visually correct state?
- Does timing match distance and importance?
- Does stagger reveal hierarchy or make the user wait?
- Can input interrupt it safely?
- Does it remain smooth on representative hardware?

## Common motion defects

- Uniform fade-up reveals flatten hierarchy. Assign different behavior to different roles or leave content still.
- Slow primary controls feel broken. Shorten feedback and remove interaction-blocking delays.
- Aggressive parallax breaks spatial coherence or legibility. Reduce range or remove it.
- Excessive pinning obscures page progress. Bound the sequence and restore normal flow.
- Hover effects shift layout or hit targets. Animate a contained visual layer instead.
- Scroll smoothing fights keyboard, anchors, or touch. Repair integration or return to native scrolling.
- Hidden initial states flash or remain hidden without JavaScript. Establish progressive fallback and initialization order.

Verify the reduced-motion version separately; it must preserve content order, visibility, and state feedback.
