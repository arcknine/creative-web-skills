# Rapid production handoff

Apply this sequence only after the user separately approves production integration.

## Implement the selection

1. Record the starting branch, worktree state, selected variant or hybrid, and the bounded UI question it resolves.
2. Port the selected presentation into the existing component architecture while keeping the variants available for comparison. Reuse established data and behavior; replace mocks and prototype-only shortcuts.
3. Render the production surface in the comparison state and exercise every behavior touched by the integration. Run checks proportional to those boundaries. Treat commits and partial passing checks as progress, not completion.

Report completion only when the whole approved surface is implemented and verified. Report a genuine blocker with the unmet criterion instead of presenting partial integration as done.

## Preserve and remove the variants

After production validation:

1. When Git is available, create a collision-free `design/<scope>-variants` archive branch containing every variant, the switcher, mocks, scoped styles, and experiment-only assets. Exclude unrelated changes, secrets, caches, and generated output. Verify and record the archive commit before cleanup.
2. Record the selection rationale and archive location in the final handoff or an already in-scope implementation record.
3. Return to the production line. Remove variant routes, switches, mocks, styles, assets, and dependencies created only for comparison. Search imports, routes, tests, stories, localization, and package usage before deleting uncertain consumers.
4. Re-run affected reference searches and checks after cleanup. Commit locally; push only when requested.

When Git is unavailable, retain the isolated variants, report that no archive branch was created, and remove them only with user approval.

## Completion criteria

- The selected presentation and preserved behavior pass targeted production validation.
- The archive restores every variant when Git is available; otherwise the retained lab is reported.
- Production contains no comparison machinery or redesign-created orphan after approved cleanup.
