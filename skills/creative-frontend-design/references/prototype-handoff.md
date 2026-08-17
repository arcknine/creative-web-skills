# Production adoption and exploration record

Complete the approved production design before retiring the design lab. Apply this handoff only after the user separately approves production integration.

## Adopt the approved direction

1. Summarize the selected direction or hybrid and the design problem it resolves as a compact production brief.
2. Inventory the behavior and production boundaries that must survive the redesign. Implement the brief through the existing application architecture while the lab remains available for visual comparison. Replace mocks with established data flows and preserve authentication, authorization, validation, analytics, transactions, business rules, background jobs, and stable behavior.
3. Compare the production result with the approved direction and exercise the preserved behavior. Continue until every approved surface is present and every risk-proportionate check passes. A commit, clean checkpoint, passing subset, or long turn marks progress only.

Report completion only after the whole approved production surface works. When a genuine blocker prevents that outcome, name the unmet criterion and report the integration as blocked.

## Preserve the design exploration

After production passes validation, record the starting production branch and worktree state, then:

1. Inventory every prototype or variant, switcher, mock, scoped style, asset, and experimental dependency created by the exploration.
2. Create a collision-free archive branch such as `design/<scope>-prototypes` or, for lightweight variants, `design/<scope>-variants`. Commit the complete exploration there, including approved, rejected, and hybrid directions. Exclude unrelated user changes, secrets, caches, and generated output.
3. Record the archive branch and commit ID. Verify that the commit restores every direction before removing exploration artifacts from the production line.
4. Record the archive location, production brief, and selection rationale in the final handoff or an implementation record already in scope.
5. Return to the production line and remove prototype routes and components, variant gates, comparison controls, mocks, scoped styles, experimental assets, and lab-only dependencies. Keep the shipped implementation free of design-lab machinery.

## Remove redesign-created orphans

Audit files and dependencies touched or superseded by the redesign. Check static and dynamic imports, routes, assets, styles, tests, stories, localization, build entries, and package usage before deletion. Remove each item proven unused because of this integration. Keep unrelated pre-existing dead code outside scope and retain uncertain dynamic consumers until their use is resolved.

Re-run reference searches and relevant build or type checks after cleanup. Commit locally; push only when the user explicitly requests it.

When Git is unavailable, keep the isolated lab, report that no archive branch was created, and remove it only with user approval.

## Completion criteria

- The approved direction is fully implemented and validated before archival begins.
- The recorded archive commit restores every explored direction when Git is available; otherwise the retained lab is reported.
- The production brief, selection rationale, and archive location are recorded durably.
- The production line contains the shipped design with no exploration machinery or redesign-created orphan.
