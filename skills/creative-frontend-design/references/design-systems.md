# Design systems without template gravity

Build a small visual grammar that preserves the concept. Do not turn every design into the same component library.

## Separate invariants from expressions

Define invariants for accessibility and consistency: focus treatment, control sizing, type roles, spacing rhythm, color roles, grid anchors, media behavior, and motion tokens. Let expressive sections vary in composition, crop, scale, and density while using those invariants.

Create semantic tokens before component aliases:

```css
:root {
  --color-field: #f2efe7;
  --color-ink: #151515;
  --color-signal: #d83a2e;
  --space-edge: clamp(1rem, 3vw, 3rem);
  --space-section: clamp(5rem, 12vw, 11rem);
  --radius-control: 0.25rem;
  --ease-enter: cubic-bezier(.16, 1, .3, 1);
}
```

Name roles by intent, not their current value. `--color-signal` survives a palette change; `--red-500` describes an implementation.

## Control component sameness

Create a component when behavior, semantics, or a repeated visual contract is genuinely shared. Do not abstract two superficially similar editorial arrangements into a universal card. Support controlled variants with a small explicit API; avoid dozens of booleans that hide unrelated compositions behind one component.

Use primitives for container edges, typography roles, buttons, links, media frames, focus, and recurring metadata. Let feature sections compose those primitives differently. A system is successful when pages feel related without appearing cloned.

## Audit the token signature

Before finalizing, inspect radius, shadow, border, blur, gradient, spacing, and container usage. If the same values appear on nearly every element, the tokens are flattening hierarchy. Reserve strong treatments for named roles and allow `none` to be the default for decoration.

Document only decisions that future sections must preserve. The rendered interface—not token count—is the completion test.
