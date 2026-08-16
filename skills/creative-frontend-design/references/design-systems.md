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

## Centralize tunable values

Treat visual values as design decisions, not markup trivia. In production and shared styles, use an existing semantic token or define one before introducing a tunable font size, line-height, spacing, width, radius, color, shadow, z-index, duration, or easing value.

Avoid hard-coded arbitrary Tailwind utilities such as `text-[12px]`, `mt-[37px]`, `rounded-[18px]`, or `shadow-[...]` when the value represents a design-system decision. Register the value in the project's Tailwind theme/configuration or expose it as a CSS custom property, then consume the named role:

```css
:root {
  --text-meta: 0.75rem;
  --leading-meta: 1.25;
  --space-section-intro: clamp(3rem, 7vw, 7rem);
}

.metadata {
  font-size: var(--text-meta);
  line-height: var(--leading-meta);
  margin-block-start: var(--space-section-intro);
}
```

```html
<!-- Prefer a project-defined semantic utility. -->
<p class="text-meta">Updated 3 hours ago</p>

<!-- Avoid embedding a design decision at the call site. -->
<p class="text-[12px]">Updated 3 hours ago</p>
```

Name the role, not the number: use `--text-meta`, `--space-hero-copy`, or `--radius-control`, not `--size-12`, `--gap-37`, or `--radius-18`. Keep component-specific variables near the component; promote values to global tokens only when multiple regions share the same contract.

A literal may remain local when it is a genuine implementation constant rather than a tunable design choice—for example, a `1px` hairline or a one-off calculation bound to an asset. Document unusual exceptions. During rapid prototype exploration, temporary literals are acceptable, but promote repeated values and every selected direction's tunable values to semantic tokens before production integration.

## Control component sameness

Create a component when behavior, semantics, or a repeated visual contract is genuinely shared. Do not abstract two superficially similar editorial arrangements into a universal card. Support controlled variants with a small explicit API; avoid dozens of booleans that hide unrelated compositions behind one component.

Use primitives for container edges, typography roles, buttons, links, media frames, focus, and recurring metadata. Let feature sections compose those primitives differently. A system is successful when pages feel related without appearing cloned.

## Audit the token signature

Before finalizing, inspect radius, shadow, border, blur, gradient, type, spacing, and container usage. Replace unexplained raw values and repeated arbitrary utilities with semantic tokens. If the same tokens appear on nearly every element, the system is flattening hierarchy; reserve strong treatments for named roles and allow `none` to be the default for decoration.

Document only decisions that future sections must preserve. The rendered interface—not token count—is the completion test.
