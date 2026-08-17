# Prototype-first workflow

Use this workflow to separate visual exploration from production integration. Optimize for directional learning first and production confidence only after approval.

## Contents

- [Choose the branch](#choose-the-branch)
- [Set up the lab](#set-up-the-lab)
- [Add a comparison dock](#add-a-comparison-dock)
- [Create three real alternatives](#create-three-real-alternatives)
- [Use realistic mock data](#use-realistic-mock-data)
- [Protect production](#protect-production)
- [Apply the smallest useful validation](#apply-the-smallest-useful-validation)
- [Compare and select](#compare-and-select)
- [Refine and visually verify](#refine-and-visually-verify)
- [Integrate the approved specification](#integrate-the-approved-specification)
- [Validate production](#validate-production)

## Choose the branch

Enter prototype mode immediately for explicit requests containing prototype, mock it first, design only, exploration, concepts, directions, isolated version, do not touch backend, or do not change working code.

Use three prototypes by default for:

- a new homepage or landing page;
- a major visual redesign;
- a substantial section whose hierarchy or art direction is unresolved;
- a new brand, campaign, portfolio, game, hospitality, sports, fashion, or editorial direction;
- an experiment where typography, composition, imagery, interaction, or motion could change materially.

Stay on one direction when the user requests one concept or another explicit count, changes a local detail, asks to iterate a named prototype, refines an approved direction, or begins integration. Treat three as the default exploration count, not a quota.

## Set up the lab

Choose the lightest isolated environment the framework supports. Prefer routes or entry points such as:

```text
/design-lab/homepage
/design-lab/homepage/a
/design-lab/homepage/b
/design-lab/homepage/c
```

Equivalent component stories, static entries, or `/prototypes/homepage-01` routes are valid. Keep URLs stable enough for screenshot comparison. An index may provide direction summaries and thumbnails, but it is not the primary navigation between prototypes.

Keep prototype styles scoped so they cannot leak into production routes. Reuse safe project primitives—reset, font loading, icon access, media utilities—only when they accelerate work without constraining divergence.

## Add a comparison dock

For two or more directions, render one lightweight shared switcher on every prototype route. Make it a fixed floating dock—typically bottom-center or in a safe corner—that lets the user open A, B, C, and the optional overview directly. Use the framework router and prefetch when available so switching feels immediate; avoid a transition that obscures visual comparison.

Keep the dock visually neutral and independent from every prototype's art direction. Scope its styles, place it above prototype content, respect safe-area insets, and prevent it from changing page layout. Make it compact or horizontally scrollable on narrow screens rather than covering the design.

Meet this interaction contract:

- identify the control with an accessible label such as `Prototype switcher`;
- expose every direction by a short name or letter and mark the current route with `aria-current="page"` plus a non-color visual state;
- use real links when each direction has a URL, preserving open-in-new-tab and browser history behavior;
- provide visible focus and touch-friendly targets;
- support optional shortcuts such as `Alt+1`, `Alt+2`, and `Alt+3` only when they do not intercept typing in inputs or editable content;
- keep the current mock-data scenario or shared query state when switching where practical;
- provide collapse or hide behavior for unobstructed inspection and screenshots, with a discoverable way to restore the dock;
- keep the dock and its dependencies out of production routes and bundles.

Do not blindly preserve raw scroll pixels between directions with different content lengths. Preserve a shared section anchor or named comparison state when the prototypes have equivalent landmarks; otherwise start at a predictable position.

The dock is the one intentional shared UI primitive across prototypes. Do not use it as a reason to force the prototypes themselves through common layout or component abstractions.

## Create three real alternatives

Write a one-paragraph thesis for A, B, and C before implementation. Derive them from the brief rather than default labels. Make at least three high-leverage systems differ across every pair:

- dominant focal point and hero logic;
- typography voice and scale behavior;
- grid, alignment, overlap, and negative space;
- section order, density, and transition rhythm;
- imagery crop, layering, and media role;
- palette structure and material treatment;
- navigation and content presentation;
- interaction and motion character;
- mobile transformation.

Do not count token swaps as separate directions. If A and B share the same DOM composition, hierarchy, crop, and interaction and differ mostly in color or font, replace one.

Use the same core content and comparable scope. Bring each prototype far enough to judge the full design language—usually hero, navigation, two or more representative section types, a primary action, and a credible mobile transformation. Keep fidelity balanced; a polished A cannot be compared fairly with skeletal B and C.

## Use realistic mock data

Create one small shared mock-data layer when practical, while allowing each prototype to select and order it differently. Mock users, products, characters, articles, prices, statistics, leaderboards, navigation, API responses, media, and application states without connecting production services.

Include content stressors:

- very short and very long titles;
- missing descriptions, images, or optional metadata;
- long names and large numbers;
- multiple status or selection states;
- portrait, landscape, square, and unusual image ratios;
- realistic list sizes rather than three perfect items.

Label invented proof, metrics, quotes, and testimonials as mock content. Do not let synthetic marketing claims survive integration unnoticed.

## Protect production

During exploration, leave backend logic, controllers, APIs, database models, authentication, authorization, payments, jobs, server workflows, and stable production components unchanged. Do not add migrations, production endpoints, or state management merely to make a prototype look live.

Read from safe existing assets or types when useful, but copy or adapt presentation-facing shapes into mock data. Do not write to production stores. Keep experimental dependencies local and avoid adding a heavy package to the production bundle before the selected direction proves it necessary.

## Apply the smallest useful validation

Validate the question being answered, not the whole repository:

| Change | Prototype-mode validation |
| --- | --- |
| Color, spacing, type size, crop, or layout | Render the affected route; inspect the relevant viewport and obvious overflow |
| Prototype component behavior | Exercise that component and check relevant console/runtime errors |
| Comparison dock | Switch from every direction, confirm active/focus states, test narrow screens, and verify hide/restore behavior |
| Responsive composition | Inspect the affected breakpoints plus one width on each side of the transition |
| Animation or interaction | Observe trigger, interruption, final state, touch behavior, and reduced-motion alternative |
| Shared mock-data shape | Render all prototypes that consume it and include one edge case |
| New experimental dependency | Confirm the prototype loads and the dependency is scoped away from production entry points |

During active iteration, skip full backend/frontend suites, repository-wide lint and type checking, full E2E, and production builds unless the prototype cannot function without them. Record deferred checks when the experiment exposes a real production risk.

Avoid premature abstractions, production APIs, authentication wiring, business-logic refactors, elaborate state management, migrations, and extensive tests. Optimize in order for art direction, identity, composition, typography, imagery, responsive behavior, interaction, motion, and internal consistency.

## Compare and select

Capture all directions with the same viewport set, core content, and relevant state. Provide a compact comparison:

```text
Direction A — thesis
Strongest at: ...
Tradeoff: ...

Direction B — thesis
Strongest at: ...
Tradeoff: ...

Direction C — thesis
Strongest at: ...
Tradeoff: ...
```

Compare concept, hero, type, composition, imagery, navigation, section rhythm, interaction, motion, and mobile potential. Do not announce a winner unless requested. Ask the user to select A, B, C, or a named hybrid before integration.

## Refine and visually verify

Keep rejected prototypes available for reference and stop polishing them. Consolidate selected ideas into one refined prototype when the user requests a hybrid. Small revisions stay within that prototype; create another direction only when the user asks or the selected thesis fails fundamentally.

Use `motion-art-direction` for the refined prototype's substantial choreography, allowing exploratory implementation to remain local until the language is approved. Use `frontend-visual-qa` against the isolated refined prototype. Inspect desktop, tablet, mobile, hierarchy, typography, crops, spacing, rhythm, motion, interaction, accessibility basics, and mock-data stressors before integration.

Before changing production code, execute [prototype archive and production handoff](prototype-handoff.md). When Git is unavailable, preserve every direction in the isolated lab, report that no branch checkpoint can be created, and obtain direction before integration.

## Integrate the approved specification

Treat the approved prototype as the presentation source of truth and the existing application as the behavior source of truth:

```text
APPROVED PROTOTYPE + EXISTING BUSINESS LOGIC -> FINAL IMPLEMENTATION
```

Port the visual hierarchy, tokens, layouts, media behavior, interactions, and approved motion into production architecture. Replace mock data with existing APIs and application state. Reconcile loading, empty, error, permission, authenticated, and transactional states. Preserve contracts, authorization, validation, analytics, and business rules.

Refactor only what integration requires. Do not use a redesign to rewrite unrelated application code or replace proven logic with prototype shortcuts.

## Validate production

After integration, identify every production boundary changed and choose checks that cover it. Run relevant type checking, linting, builds, unit tests, component tests, integration tests, backend tests, E2E flows, visual regression, accessibility checks, and performance measurement.

Broaden validation when shared components, routing, data contracts, authentication, transactions, or build behavior changed. Keep it targeted when the approved presentation is isolated and the evidence covers the affected surface. Finish only when the production page matches the approved prototype and existing behavior still works.
