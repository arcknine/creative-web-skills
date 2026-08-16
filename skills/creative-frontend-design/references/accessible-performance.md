# Accessible performance

Treat accessibility and speed as art-direction inputs. Preserve the intended hierarchy and atmosphere under keyboard input, reduced motion, zoom, slow networks, and small devices.

## Structure before styling

- Keep DOM order aligned with reading and focus order even when the layout is visually broken or overlapping.
- Use native landmarks, headings, links, buttons, labels, and disclosure controls before recreating behavior with generic elements.
- Give every interaction a visible keyboard focus state that belongs to the visual language.
- Keep tap targets operable without relying on hover or cursor-following behavior.
- Make image and video alternatives match purpose: informative alt text, empty alt for decoration, captions/transcripts where content requires them.
- Verify zoom, text resizing, long translations, and forced/high-contrast modes when the target platform supports them.

## Budget the spectacle

Identify the likely largest-content element, critical fonts, hero media, and above-fold JavaScript before implementation. Prioritize only what the first composition needs. Defer below-fold media and nonessential animation code.

- Reserve media dimensions to prevent layout shift.
- Use responsive image sources sized to the rendered slot.
- Subset and self-host fonts when licensing permits; limit families, weights, and blocking requests.
- Prefer CSS and platform behavior for simple interactions.
- Lazy-load 3D, video, and heavy motion modules behind capability and visibility checks.
- Do not ship desktop-scale media to narrow screens when an art-directed source is available.

## Design failure states

The page must retain content, hierarchy, and actions when custom fonts are late, images fail, JavaScript is unavailable, animation is reduced, or a low-power device drops effects. Progressive enhancement is part of the visual system.

Measure the built page rather than declaring it fast from implementation choices. Inspect loading, layout stability, responsiveness, and animation smoothness on representative mobile hardware and a throttled connection. Remove or simplify the least valuable effect first.
