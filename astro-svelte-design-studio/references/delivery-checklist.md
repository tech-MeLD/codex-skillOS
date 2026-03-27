# Delivery Checklist

## Visual hierarchy

- Does the page make its main promise visible in the first viewport?
- Is there one dominant CTA path instead of competing button styles?
- Do section backgrounds, spacing, and type scale create clear rhythm?
- Are cards and borders consistent with the chosen design system?

## Responsive behavior

- Check at roughly 375px, 768px, 1024px, and 1440px widths.
- Confirm headings wrap cleanly without awkward widows.
- Ensure grids collapse intentionally, not by accident.
- Verify tap targets remain comfortable on mobile.

## Accessibility

- Confirm color contrast is still strong on tinted or textured backgrounds.
- Ensure keyboard users can reach all interactive controls.
- Keep focus styles visible and visually related to the component.
- Use semantic headings and landmark regions.
- Respect `prefers-reduced-motion` for reveal sequences and widgets.

## Performance

- Hydrate only components that genuinely need client behavior.
- Prefer `client:visible` or `client:idle` over `client:load` when possible.
- Avoid oversized web font sets and unnecessary animation libraries.
- Keep above-the-fold content meaningful before JavaScript runs.

## Astro and Svelte boundary check

- Are static sections still in Astro instead of drifting into Svelte?
- Are island props simple and serializable?
- Do token variables live in shared CSS instead of being redefined per component?
- Is each island solving a clear interaction problem?

## Content quality

- Replace placeholder copy or make assumptions explicit.
- Match tone to the industry and price point.
- Verify proof elements are believable and placed near decision moments.
- End with a CTA that feels proportionate to the user's commitment level.
