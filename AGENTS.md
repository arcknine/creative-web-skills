# Repository guidance

This repository contains reusable Agent Skills for AI coding agents. Inspect every existing skill and its references before adding or changing rules; extend the closest source of truth instead of creating duplicates.

## Authoring rules

- Keep each skill focused and opinionated. Prefer decisions, procedures, thresholds, and checks over generic design advice.
- Write for an autonomous coding agent, using actionable imperatives and observable completion criteria.
- Keep `SKILL.md` concise. Put branch-specific techniques, examples, and deep knowledge in directly linked `references/` files, and state exactly when each file should be read.
- Keep each rule in one authoritative location and cross-reference it elsewhere.
- Name anti-patterns and pair them with a constructive alternative.
- Preserve semantic HTML, accessibility, keyboard behavior, readable contrast, reduced-motion support, image optimization, and performance.
- Treat references as inspiration for principles, never as templates. Do not reproduce branding, copy, assets, distinctive illustrations, exact layouts, or signature motion sequences.
- Favor original art direction derived from the product, audience, and content. Never instruct an agent to clone a reference website.
- Keep Markdown readable and portable. The `name` must match its directory; the `description` must state both what the skill does and the concrete tasks that should trigger it. Default to only those two frontmatter fields unless a standard optional field is genuinely required.
- Keep product metadata outside the portable core. `agents/openai.yaml` may improve Codex presentation but must not be required to understand or run a skill.

Before finishing a change, run `npx skills add . --list`, validate every affected skill against the Agent Skills specification, inspect cross-links, search for duplicated guidance, and verify that instructions remain agent-oriented.
