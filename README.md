# Creative Web Skills

**Agent skills for building websites that don't look AI-generated.**

Creative Web Skills packages reusable art direction, motion direction, and visual QA workflows for coding agents that support the [Agent Skills format](https://agentskills.io/specification), including Codex, Claude Code, Cursor, and compatible tools.

## Why this exists

Frontend agents can write correct components while still converging on the same centered hero, rounded cards, gradient glow, and uniform reveal animation. These skills move the design process upstream: explore distinct visual theses, compare them in working prototypes, refine an approved direction, integrate it responsibly, then inspect the rendered result until it holds together.

The aim is not to reproduce any reference site. It is to extract transferable principles—hierarchy, rhythm, cropping, restraint, contrast—and apply them to the actual brand and content.

## Included skills

| Skill | Purpose |
| --- | --- |
| `creative-frontend-design` | Explore three isolated directions by default, then art-direct and integrate the approved public-facing website. |
| `motion-art-direction` | Define and build intentional motion, scroll choreography, transitions, and micro-interactions. |
| `frontend-visual-qa` | Review rendered pages, prioritize visual defects, implement targeted fixes, and verify again. |

## Compatibility

The portable core of each package is a spec-compliant `SKILL.md` plus relative links to optional references and examples. The skills declare no runtime, MCP, framework, or operating-system dependency. Agents may use whatever frontend stack and browser tooling the project already provides.

`frontend-visual-qa` needs rendered browser or screenshot evidence to claim visual verification. Without those capabilities it can still review supplied screenshots and code, but it must label unobserved behavior as unverified.

## Prototype-first workflow

For a new homepage, landing page, major redesign, or substantial section redesign, `creative-frontend-design` creates three meaningfully different isolated prototypes by default. It compares them with shared content, waits for the user's selection, refines and visually verifies the chosen direction, then integrates that visual specification with the application's existing business logic.

Three is a default, not a constraint. Users can request one or five directions, combine ideas across prototypes, or iterate a named direction. Small changes to an approved design stay on that design and do not create three new prototypes.

## Installation

Preview the skills before installing:

```bash
npx skills add arcknine/creative-web-skills --list
```

Install the collection interactively with the [Skills CLI](https://www.skills.sh/docs/cli):

```bash
npx skills add arcknine/creative-web-skills
```

Install one skill:

```bash
npx skills add arcknine/creative-web-skills --skill creative-frontend-design
```

Install several skills:

```bash
npx skills add arcknine/creative-web-skills --skill creative-frontend-design --skill motion-art-direction --skill frontend-visual-qa
```

The CLI installs at project scope by default and can detect supported agents. Use `-g` for a user-level install and `-a` to choose an agent explicitly:

```bash
npx skills add arcknine/creative-web-skills -g -a codex
npx skills add arcknine/creative-web-skills -g -a claude-code
```

Add `-y` for a non-interactive install. Agent tooling evolves, so check the linked CLI documentation before pinning these commands in automation.

Validate a local checkout without installing it:

```bash
npx skills add . --list
```

## Updating installed skills

Update one project-scoped skill installed through the Skills CLI:

```bash
npx skills update creative-frontend-design -p
```

Update one globally installed skill:

```bash
npx skills update creative-frontend-design -g
```

Update all installed skills in the selected scope:

```bash
npx skills update
```

Pass multiple names to update this collection together, and add `-y` to skip the scope prompt:

```bash
npx skills update creative-frontend-design motion-art-direction frontend-visual-qa -y
```

The update command relies on source information recorded during CLI installation. If a skill was copied manually, reinstall it with `npx skills add arcknine/creative-web-skills` so future updates can be tracked.

## Claude Code

Claude Code supports the Agent Skills format and can invoke a skill automatically from its description or directly as `/skill-name`. Use the targeted CLI command above, or copy a complete skill folder to `~/.claude/skills/` for user scope or `.claude/skills/` for project scope. See [Claude Code's skills documentation](https://code.claude.com/docs/en/skills) for discovery and precedence behavior.

## Codex

Use the targeted CLI command above and confirm all three names appear in Codex's available-skills list. Invoke one explicitly with `$creative-frontend-design`, `$motion-art-direction`, or `$frontend-visual-qa`, or describe a matching task and allow Codex to select it from the trigger description.

Each skill also includes `agents/openai.yaml` for Codex-facing display metadata. This optional product metadata sits outside the portable `SKILL.md` core and does not change behavior in agents that ignore it.

## Cursor

Use the Skills CLI with `-a cursor`. Keep the complete skill directory so references and examples remain available; copying only `SKILL.md` discards much of the guidance.

## Usage

Name a skill explicitly when you want predictable behavior. Supply the product, audience, content, constraints, available assets, and any references. References define a quality bar—not a copying target. Use the skills separately when possible; combine all three only when the task includes design, motion, and rendered verification.

```text
Use the creative-frontend-design skill.

Prototype a premium homepage for a competitive fantasy game.

Visual direction:
dark editorial sports photography meets fantasy tournament branding.

Avoid generic SaaS UI.

Use oversized typography, full-bleed character artwork,
asymmetric composition, and restrained GSAP scroll choreography.

Create three distinct isolated directions with realistic shared mock content.
Compare them visually and wait for my selection before integration.
```

Combine all three skills for an implementation-and-review loop:

```text
Use creative-frontend-design, motion-art-direction, and frontend-visual-qa.
Art-direct and build a launch site for a coastal boutique hotel.
First create three isolated, genuinely different directions and compare them.
Do not change production code until I select a direction.
Then refine the selected prototype, apply its responsive motion language,
run visual QA against the prototype, integrate it with existing logic,
and perform production validation proportional to the integration risk.
```

## Example prompts

- “Use `creative-frontend-design` to redesign this portfolio around the artist's archival process. Keep the existing stack and content.”
- “Use `creative-frontend-design` to give me one concept only and iterate it in isolation.”
- “Use `motion-art-direction` to replace this page's uniform fade-ups with a restrained motion system tied to its editorial hierarchy.”
- “Use `frontend-visual-qa` to inspect the running page at desktop, tablet, and mobile widths; fix the highest-impact visual problems and verify again.”

## Repository structure

```text
skills/
├── creative-frontend-design/
│   ├── SKILL.md
│   ├── agents/openai.yaml
│   ├── references/
│   └── examples/
├── motion-art-direction/
│   ├── SKILL.md
│   ├── agents/openai.yaml
│   └── references/
└── frontend-visual-qa/
    ├── SKILL.md
    ├── agents/openai.yaml
    └── references/
```

Each `SKILL.md` contains the core workflow. References hold focused guidance loaded only when relevant.

## Philosophy

Start with art direction, not components. Explore substantial visual work through three distinct isolated prototypes unless the user chooses another count. Compare before committing, refine before integrating, and preserve existing business logic throughout exploration. Let content determine hierarchy. Transform compositions across breakpoints instead of shrinking them. Give motion a narrative job. Inspect pixels in the browser, because implementation is not complete until the rendered result survives critique.

Originality is a constraint: borrow principles, not protected expression. Accessibility and performance are part of premium craft, not cleanup work.

## Contributing

Read [AGENTS.md](AGENTS.md) before contributing. Keep skills narrow, guidance executable, and detailed material progressively disclosed. Avoid duplicated rules, validate frontmatter and links, and include anti-patterns with better alternatives.

## License

Released under the [MIT License](LICENSE).
