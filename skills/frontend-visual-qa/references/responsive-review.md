# Responsive review

Review responsive behavior as composition transformation, not breakpoint compliance.

## Capture matrix

Use widths that expose the design's real transitions: wide desktop, compact laptop or tablet, narrow phone, and one width immediately before a major breakpoint. Add landscape or large-text tests when the interface warrants them.

At each width, inspect:

- priority and reading order;
- headline wraps, widows, clipping, and body measure;
- subject retention and `object-position` in every crop;
- navigation capacity and touch-target spacing;
- overlaps, sticky elements, viewport units, and browser chrome;
- horizontal overflow and long unbroken content;
- section density and total page length;
- hover-dependent information on touch;
- DOM order, focus order, and zoom behavior.

## Diagnose stacked desktop

Flag mobile when it preserves desktop's every layer in a long stack, repeats excessive gaps, demotes the focal image, or leaves type timid. Prescribe a transformation: reorder, recrop, combine, remove secondary decoration, change ratio, shorten motion, or create a new mobile grouping.

Compare neighboring widths after each fix. A media query that repairs one preset but creates a jump nearby is not complete.
