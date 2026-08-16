# Page transitions

Use a route transition only when it explains continuity, preserves orientation, or creates a deliberate chapter break. Navigation feedback must begin immediately; spectacle must not make the next page feel late.

## Choose the relationship

- Use shared-element continuity when the same object clearly persists across views.
- Use a directional wipe when information architecture has a spatial direction.
- Use a brief field or mask transition for a chapter change.
- Use no transition when destinations are unrelated or navigation speed matters more than continuity.

Keep outgoing content readable until navigation is committed. Prevent double activation, preserve browser history, and move focus to the new page's meaningful start. Announce route changes where the framework does not do so. Restore or intentionally reset scroll position.

## Coordinate lifecycle

Separate exit, data/loading, and entry states. Do not let an exit animation hide a failed navigation. Bound total delay, handle rapid consecutive navigation, and cancel stale timelines. Clean up overlays and `aria-hidden` state even after interruption.

Use the framework's routing lifecycle rather than arbitrary timeouts. If the next view streams or loads asynchronously, transition to a stable shell or useful loading state instead of holding a blank cover.

Under reduced motion, replace spatial travel and scale with an immediate swap or brief opacity change while preserving focus and route announcements. Test deep links, back/forward, refresh, slow data, errors, and keyboard navigation.
