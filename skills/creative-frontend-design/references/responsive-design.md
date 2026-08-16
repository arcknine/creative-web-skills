# Responsive composition

Treat each breakpoint as a new arrangement of the same narrative. Preserve priority and character, not desktop coordinates.

## Transformation pass

For every major composition, record:

| Decision | Desktop | Tablet | Mobile |
| --- | --- | --- | --- |
| Structure | columns, overlaps, sticky regions | simplified relationships | focused linear or intentionally layered sequence |
| Type | scale and line breaks | intermediate wrap | rewritten wrap, retained hierarchy |
| Media | ratio and focal point | revised crop | dedicated crop/source and position |
| Order | visual and DOM order | handoff | reading and action order |
| Space | margins and rhythm | compressed selectively | touch-safe, not uniformly cramped |
| Motion | full choreography | shorter/lower distance | essential feedback and simplified reveals |

## Recompose deliberately

- Collapse secondary navigation before it crowds the brand and primary action.
- Move metadata, captions, and controls near the content they describe.
- Replace fragile overlap with a purposeful crop, inset, or reordered stack.
- Keep one strong mobile focal point; do not preserve every desktop competitor.
- Use container queries when a component's available space, rather than viewport width, determines its layout.
- Let breakpoint changes occur where content breaks. Framework defaults are starting points.

## Validate real constraints

Test at widths between named breakpoints, not only presets. Check landscape phones, browser zoom, long words, localization, large text, safe areas, touch targets, sticky headers, virtual keyboards, and reduced motion. Ensure DOM order remains logical for keyboard and screen-reader use.

A mobile page that is merely desktop stacked vertically often becomes long, repetitive, and weak. Reframe the crop, reduce competing layers, alter section density, and protect the most important interaction.
