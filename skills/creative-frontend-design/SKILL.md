---
name: creative-frontend-design
description: Art-direct, prototype, and implement visually distinctive public-facing websites. Use for substantial homepage, landing-page, brand, editorial, fashion, hospitality, sports, game, portfolio, or major section design and redesign; visual exploration, concepts, isolated prototypes, reference-led art direction, or replacing generic AI-generated frontend styling. Also use for small visual refinements, but keep those on the selected direction instead of creating three new concepts.
---

# Creative frontend design

Act as both a senior digital art director and a senior frontend engineer. **Do not start with components. Start with art direction.** Make the page recognizable before decorating it.

## Prototype-first default

For substantial visual design, redesign, art direction, layout, typography, animation, or frontend experimentation, prototype in isolation and create **3 distinct directions by default** unless the user specifies another number. Apply this default to a new homepage, landing page, major redesign, or substantial section redesign.

```text
UNDERSTAND -> CREATE 3 -> COMPARE -> ITERATE -> USER SELECTS -> REFINE -> VISUAL QA -> INTEGRATE -> PRODUCTION VALIDATION
```

Make the prototypes meaningfully different in concept, typography, composition, imagery, density, interaction, and motion—not cosmetic variations of one layout. Preserve working application and backend logic until the user selects or approves a direction. During exploration, use the **smallest useful validation**.

Keep a small change on an already selected direction as one change. Do not generate three prototypes for a button adjustment, spacing correction, requested iteration on prototype B, approved-direction refinement, or explicit request for one concept.

Read [prototype workflow](references/prototype-workflow.md) before coding whenever the task is substantial or the user says prototype, mock it first, design only, exploration, concepts, directions, isolated version, do not touch backend, or do not change working code.

## Workflow

### 1. Understand the scope

Inspect the repository, current design system, content, assets, routes, constraints, and stable application behavior. When references or screenshots are supplied, analyze hierarchy, typography, spacing, composition, color relationships, media treatment, navigation, section transitions, scroll behavior, interaction language, density, and motion.

Extract principles only. Create original branding, composition, copy treatment, crops, and choreography. Do not reproduce logos, proprietary text, distinctive illustrations, exact layouts, signature animation sequences, or unique assets.

Choose the prototype-first branch unless the user explicitly changes the count, asks for a small or single-direction change, names an existing prototype to iterate, or has already approved the direction and requested integration.

### 2. Frame three directions

Derive all directions from the project's brand, audience, content, assets, product, desired emotion, references, and technical constraints. Do not reuse a fixed editorial/immersive/minimal trio across projects.

Write a compact brief for A, B, and C covering:

1. Visual concept and brand personality
2. Typography language
3. Composition and grid
4. Color and imagery
5. Navigation and content order
6. Interaction and motion
7. Section rhythm and density
8. Responsive transformation

Give each direction a defensible thesis and a different dominant gesture. Use shared content to make comparison honest.

### 3. Build isolated prototypes

Create framework-appropriate routes or components such as `/design-lab/homepage/a`, `/b`, and `/c`, plus a minimal comparison index when practical. Share realistic mock data, not a rigid presentation architecture. Let prototype code remain disposable when abstraction would limit exploration.

Protect production behavior. Do not connect prototypes to real APIs, databases, authentication, payments, jobs, controllers, or stable business logic merely to preview design. Include mock-content extremes that expose visual fragility.

Bring all three prototypes to comparable directional fidelity before polishing one. For each visual edit, render the affected prototype, inspect the relevant viewport or interaction, and check obvious runtime errors. Defer repository-wide tests, builds, and unrelated refactoring.

### 4. Compare and obtain selection

Show A, B, and C with the same core content and comparable viewport evidence. Explain each philosophy and its tradeoffs across hero, type, composition, imagery, navigation, rhythm, interaction, motion, and mobile potential.

Do not choose a winner unless asked. Apply comparison feedback to the relevant prototypes and repeat until the user can select confidently. Stop before production integration and obtain the user's selection or approval. Accept hybrids such as the hero from A, typography from B, and navigation from C; consolidate them into one refined direction.

### 5. Refine and visually verify

Stop investing heavily in rejected directions, but retain them unless removal is requested. Iterate on the selected prototype; small refinements do not restart the three-prototype branch.

When `motion-art-direction` is installed, apply it inside the selected prototype for substantial choreography. When `frontend-visual-qa` is installed, apply it to the isolated refined prototype across desktop, tablet, mobile, motion, interaction, accessibility basics, and edge-case mock content.

### 6. Integrate after approval

Treat the approved prototype as a visual specification expressed in working code. Port its presentation into the application, replace mocks with real data, reuse existing APIs, preserve business rules, and adapt components to production architecture. Do not replace proven application logic with prototype logic or use redesign as permission for unrelated cleanup.

### 7. Validate production

After integration, run validation proportional to the affected production surface: type checks, linting, builds, unit, component, integration, backend, E2E, and regression tests as scope and risk require. Use targeted validation when it establishes confidence; run broad suites when integration crosses broad boundaries.

## Reference routing

- Read [visual direction](references/visual-direction.md) when the brief lacks a clear concept, and [anti-AI slop](references/anti-ai-slop.md) before evaluating any direction.
- Read [typography](references/typography.md), [layout](references/layout.md), [color](references/color.md), [imagery](references/imagery.md), and [design systems](references/design-systems.md) when changing those systems.
- Read [responsive design](references/responsive-design.md) before mobile refinement and [accessible performance](references/accessible-performance.md) before media-, interaction-, or motion-heavy implementation.
- Read [landing pages](references/landing-pages.md) or [game sites](references/game-sites.md) only for the relevant category.
- Use a relevant example as a brief format, never a template: [luxury minimal](examples/luxury-minimal.md), [sports editorial](examples/sports-editorial.md), [gaming](examples/gaming.md), or [creative agency](examples/creative-agency.md).

## Completion criteria

- A substantial exploration produces three isolated, comparable directions unless the user overrides the count.
- Each prototype has a distinct thesis and dominant gesture, not merely different colors or minor layout changes.
- The user selects or approves a direction before production integration begins.
- Existing application and backend behavior remain untouched during exploration.
- Prototype iteration uses the smallest useful validation; post-integration validation matches scope and risk.
- The approved result is original, accessible, performant, responsive, and verified in the browser.
