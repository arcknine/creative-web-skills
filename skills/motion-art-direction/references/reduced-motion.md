# Reduced motion

Treat reduced motion as an alternate direction that preserves hierarchy and state without vestibular or attention-heavy effects.

## Transform the system

- Replace parallax, large translation, rotation, zoom, and long scrubbed scenes with stable compositions or short opacity changes.
- Unpin narrative sections and expose their content in normal document flow.
- Keep necessary state transitions—menus, disclosure, validation—brief and clear rather than eliminating feedback.
- Pause autoplaying decorative video or supply a still poster when possible.
- Avoid smooth-scroll interpolation and cursor-following effects.
- Preserve final visibility; reduced-motion styles must never leave elements in hidden initial states.

```css
@media (prefers-reduced-motion: reduce) {
  *, *::before, *::after {
    scroll-behavior: auto !important;
    animation-duration: 0.01ms !important;
    animation-iteration-count: 1 !important;
    transition-duration: 0.01ms !important;
  }
}
```

The blanket rule is a safety net, not the whole design. Add component-specific variants where instant state changes would confuse or where JS-created timelines must be skipped. Test the preference at initial load and after route changes.
