---
name: creative-web-workflow
description: Coordinate a substantial complete creative-website redesign across discovery, art direction, isolated prototypes, motion, rendered visual QA, production integration, and final validation. Use for brand-level, multi-page, or full design-to-production work. Use rapid-ui-redesign when an existing working UI needs fast visual experimentation while retaining its identity and application architecture.
---

# Creative web workflow

Orchestrate the collection's three specialist skills. Keep their instructions authoritative and add only cross-skill order, approvals, and handoffs here.

## Dependency contract

Require sibling installations of [creative frontend design](../creative-frontend-design/SKILL.md), [motion art direction](../motion-art-direction/SKILL.md), and [frontend visual QA](../frontend-visual-qa/SKILL.md). Resolve all three links before starting. When any is unavailable, name the missing skill and ask the user to install the complete collection; a partial local rewrite is not this workflow.

## Workflow

### 1. Explore

Read [creative frontend design](../creative-frontend-design/SKILL.md) completely. Execute its workflow through prototype comparison. Keep its prototype-first branch, reference routing, and completion criteria authoritative.

### 2. Select

Hold its user-selection gate. Accept one direction, a hybrid, or another comparison iteration. Before pausing, report `phase: selection`, the prototype locations, rendered evidence, unresolved choices, and the exact next phase.

Resume after explicit direction approval. If the runtime does not retain skill context across turns, re-read this file and the named specialist before continuing from the reported phase.

### 3. Refine motion

Continue refinement in the approved isolated prototype. Read [motion art direction](../motion-art-direction/SKILL.md) completely and execute its workflow there. Keep both specialists' reference routing and completion criteria authoritative.

### 4. Verify and approve

Read [frontend visual QA](../frontend-visual-qa/SKILL.md) completely and execute its full evidence-and-fix loop on the refined prototype. Present the verified result and hold a second gate for explicit production-integration approval.

Before pausing, report `phase: integration approval`, the approved-direction specification, evidence locations, remaining constraints, and the exact next phase. Resume under the same context-restoration rule used after selection.

### 5. Integrate and validate

After approval, execute the design skill's prototype-checkpoint, branch-handoff, production-integration, and validation stages in order. Then execute the visual-QA skill against the production result and use the motion skill for any integration-specific motion regression. Run only the automated checks selected by the design skill's risk-proportionate validation rules.

## Completion criteria

- The phases run in order and both approval gates are satisfied when applicable.
- The design skill's prototype handoff criteria pass before production integration.
- Every specialist's applicable completion criteria pass in its own phase.
- The final handoff names the selected direction, production validation performed, rendered evidence, and any unverified risk.
