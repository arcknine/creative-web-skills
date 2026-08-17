---
name: frontend-visual-qa
description: Review and fix implemented frontends from rendered evidence. Use for screenshot or browser audits, visual critique, responsive QA, reference-fidelity checks, evidence-led polish, visual debugging, and verification of hierarchy, typography, spacing, crops, composition, motion, accessibility, or generic AI-design failures.
---

# Frontend visual QA

Treat visual QA as an implementation loop, not a written review:

```text
DESIGN → IMPLEMENT → RUN → SCREENSHOT → CRITIQUE → FIX → SCREENSHOT AGAIN → FINAL REVIEW
```

## Workflow

### 1. Establish the target

Read the brief, intended art direction, existing design system, and relevant references. Run the actual page. Preserve deliberate choices unless rendered evidence shows they fail. If implementation changes are outside the request, stop after the evidence-backed critique.

For directional comparison, review isolated prototypes with the same content, states, and viewport set; report their visual philosophies and tradeoffs without selecting a winner unless asked. After selection, perform detailed QA and fixes inside the refined prototype before production integration.

### 2. Capture representative evidence

Read [browser evidence](references/browser-evidence.md), then inspect at least one wide desktop, one intermediate/tablet width, and one narrow mobile width. Add relevant states: menu open, hover, focus, long content, empty/error, reduced motion, or animation mid-sequence. Capture full-page context and focused crops when needed. Read [visual review](references/visual-review.md) and [responsive review](references/responsive-review.md).

If no browser or screenshot capability is available, review the supplied evidence and code, label unobserved behavior as unverified, and do not claim visual completion.

### 3. Critique by impact

Evaluate first impression, hero composition, visual identity, hierarchy, typography, spacing, rhythm, image crops, color balance, alignment, consistency, section transitions, mobile composition, overflow, motion, hover/focus states, accessibility, and finish.

Read [common failures](references/common-failures.md) and use it to diagnose hierarchy, identity, composition, type, crop, responsive, contrast, and motion failures. Do not paste the checklist into the critique; report only issues visible in the evidence.

Report findings in this form:

```text
HIGH IMPACT

1. Hero lacks a dominant focal point.
   The headline, image, and CTA compete equally.
   Increase headline scale and reduce supporting-copy weight.

2. Section 3 reads as generic SaaS UI.
   Replace the three identical cards with an asymmetric editorial composition.

MEDIUM IMPACT
...

POLISH
...
```

Tie every finding to visible evidence, explain why it weakens the direction, and prescribe a bounded fix. Prioritize the few changes that improve hierarchy and identity across the largest area. Do not churn unrelated details.

### 4. Implement the fixes

Fix high-impact issues first, then medium issues, then polish that still matters. Work with the current component and token system. Correct root causes—layout rules, type scale, crop strategy, spacing rhythm—not isolated screenshots. Preserve semantics, keyboard behavior, contrast, reduced motion, and performance. In prototype mode, change only the selected or explicitly named direction.

For animation, inspect load, scroll, reverse scroll, hover, focus, touch, and exit behavior using [motion review](references/motion-review.md).

### 5. Verify again

Rerun and recapture the same viewports and states. Compare before and after against each finding. Check that a desktop fix did not regress mobile, that crops retain subjects, and that motion settles correctly. Repeat only while a material issue remains.

## Completion criteria

- Every high-impact finding is fixed or explicitly constrained by the brief.
- Final screenshots demonstrate stronger hierarchy, identity, composition, and responsive behavior.
- No new overflow, interaction, accessibility, motion, or performance regression is visible.
- The final review distinguishes resolved items from remaining medium or polish concerns.
