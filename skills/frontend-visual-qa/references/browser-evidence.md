# Browser evidence

Base visual conclusions on rendered evidence. Source code can suggest a defect but cannot prove composition, crop, font rendering, animation timing, or browser overflow.

## Prepare

1. Identify the canonical run command from the repository rather than inventing one.
2. Record the route, state, data assumptions, viewport, device scale, color scheme, and reduced-motion setting.
3. Wait for fonts and intentional entrance motion to settle unless reviewing an in-motion frame.
4. Keep console and network failures visible; a polished screenshot can conceal a broken page.

## Capture a reproducible set

- Capture the same route at wide, intermediate, and narrow widths.
- Capture a full-page view for rhythm and focused views for type, alignment, and state details.
- Exercise navigation, hover, keyboard focus, touch-equivalent states, menus, forms, and sticky regions.
- Capture before and after at identical dimensions and state.
- Name evidence by route, viewport, state, and pass so comparisons cannot be confused.

Avoid relying on one arbitrary mobile preset. Include widths immediately before or after layout transitions when those are likely failure points.

## Distinguish evidence levels

Label findings as:

- **Observed:** visible in a rendered state you inspected.
- **Reproduced:** observed repeatedly with documented steps.
- **Code-indicated:** inferred from source but not rendered.
- **Unverified:** outside available tools, routes, data, or states.

Only observed or reproduced evidence can close a visual finding. After changes, rerun the same evidence set and check adjacent widths so a local fix does not become a breakpoint regression.
