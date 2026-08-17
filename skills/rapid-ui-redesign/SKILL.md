---
name: rapid-ui-redesign
description: Rapidly redesign the visual presentation of an existing working UI through isolated, switchable variants while preserving its identity, application architecture, data contracts, and business behavior. Use for fast experiments on an existing page, dashboard, navigation, section, or component. Use creative-frontend-design for deeper original art direction and creative-web-workflow for complete discovery-to-production redesigns.
---

# Rapid UI redesign

Answer one localized visual question quickly. Preserve the existing product context and avoid expanding the task into full art direction.

## Scope gate

Use this workflow when the target already works and the redesign retains its identity, data contracts, and primary behavior. Inspect only the target UI, its immediate presentation dependencies, and the contracts needed to reproduce it; expand outward only when evidence requires it.

Choose the branch before coding:

- Create three variants by default for an open-ended redesign, a new visual direction, or a substantially different navigation or hierarchy, even when the target is one existing homepage or dashboard.
- Stay on one variant for a fully specified mechanical change, an explicit one-direction request, an approved direction, or an iteration on a named variant such as prototype B.
- Escalate to `creative-frontend-design` when the task needs deep original art direction beyond the existing identity.
- Escalate to `creative-web-workflow` when it needs discovery, new identity or information architecture, coordinated multi-page work, substantial motion direction, systematic visual QA, and production integration as one complete lifecycle.

## Workflow

### 1. Frame one question

Inspect the rendered target, existing design system, representative content, relevant states, and stable behavior. State the decision in one sentence, such as “Which hierarchy makes the account summary easiest to scan?” Bound the presentation surface that may change.

### 2. Build lightweight variants

Create the count chosen at the scope gate. Make multiple variants structurally different in layout, hierarchy, density, or primary affordance while retaining the existing identity and component language. Keep scope comparable and use the same content.

Prefer an isolated dev-only route such as `/design-lab/rapid/<scope>?variant=A`, component story, or equivalent lab entry. Reuse safe presentational primitives and copy the minimum data shapes needed for fidelity. Use representative mock data by default; use a read-only adapter only when live shape or density is essential. Do not connect prototype variants to production mutations, controllers, APIs, models, authentication, authorization, payments, business rules, background jobs, or stable workflows.

### 3. Add one comparison control

Provide a compact development-only switcher with direct variant access, current-state indication, keyboard operation, visible focus, and stable URLs. Keep it visually separate from the candidate designs and excluded from production builds.

### 4. Validate only the question

Render each variant in the most relevant viewport and state, check obvious overflow and runtime errors, and exercise the changed interaction. Add adjacent widths, touch, keyboard, or reduced motion only when the localized decision affects them. Defer repository-wide lint, type checking, builds, backend tests, E2E, and broad regression suites during comparison.

### 5. Compare and select

Present every variant with the same state and a short strongest-at/tradeoff comparison. Ask the user to select one, request a revision, or name a hybrid. Selection approves the direction, not production integration; stop and obtain separate integration approval before production changes.

### 6. Archive and fold in

After separate integration approval, read and execute [prototype archive and production handoff](../creative-frontend-design/references/prototype-handoff.md), using `design/<scope>-variants` for the archive branch. Rewrite the selected direction in the existing production component; do not promote prototype shortcuts directly.

### 7. Verify the production change

Read [accessible performance](../creative-frontend-design/references/accessible-performance.md). Repeat the targeted evidence used for comparison and run automated checks proportional to the production surface changed. Broaden validation only when the fold-in crosses shared components, routing, data contracts, or application behavior. Use `frontend-visual-qa` only when the user requests deep systematic review or the integration exposes material visual uncertainty.

## Completion criteria

- The work answers one bounded UI question without changing the wider brand or application architecture.
- Variants differ structurally, remain cheap to compare, and preserve stable product context.
- The user selects or defines the result before production code changes.
- The shared prototype handoff criteria pass before integration, and the production result preserves semantics, keyboard behavior, contrast, reduced motion, image delivery, and performance.
- The production implementation preserves existing behavior and passes targeted rendered and automated validation.
