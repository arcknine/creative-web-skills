# Prototype archive and production handoff

Preserve exploration before production integration. Apply this handoff only after the user separately approves integration.

## Archive the complete exploration

1. Inspect the current branch and worktree. Inventory every prototype or variant, switcher, mock, scoped style, asset, and experimental dependency created by the exploration.
2. Create a collision-free archive branch such as `design/<scope>-prototypes` or, for lightweight variants, `design/<scope>-variants`.
3. Stage the complete exploration with explicit paths and commit one checkpoint containing approved, rejected, and hybrid directions. Exclude unrelated user changes, secrets, caches, generated output, and production edits outside the lab.
4. Record the archive branch and commit ID. Before deleting any exploration artifact, verify that the commit contains every direction and that the archive can be checked out. Stop when this proof fails or when overlapping user changes make the checkpoint unsafe.

## Create the production-only branch

1. Create `design/<scope>-integration` from the verified archive checkpoint.
2. Remove the entire exploration layer from the integration branch: prototype routes and components, variant gates, comparison controls, mocks, scoped styles, experimental assets, and lab-only dependencies. Retain a file only when deliberately converting it into a production asset or component.
3. Implement the approved visual specification directly in the existing production architecture. Preserve established data flows, authentication, authorization, validation, analytics, transactions, business rules, background jobs, and stable behavior.

## Remove redesign-created orphans

Audit files and dependencies touched or superseded by the redesign. Check static and dynamic imports, routes, assets, styles, tests, stories, localization, build entries, and package usage before deletion. Remove each item proven unused because of this integration. Keep unrelated pre-existing dead code outside scope and retain uncertain dynamic consumers until their use is resolved.

Re-run reference searches and relevant build or type checks after cleanup. Commit locally; push only when the user explicitly requests it.

## Completion criteria

- The recorded archive commit can restore every explored direction before cleanup starts.
- The integration branch contains no exploration machinery or redesign-created orphan.
- The selected design is implemented through production architecture without unrelated behavior changes.
