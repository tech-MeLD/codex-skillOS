# Astro Patterns

## Default project shape

Use Astro as the structural layer.

- `src/layouts/`: document shell, shared metadata, header/footer frame
- `src/components/sections/`: mostly static content sections
- `src/components/ui/`: reusable buttons, cards, badges, wrappers
- `src/components/islands/`: Svelte entry points only
- `src/styles/`: tokens, global styles, utility layers
- `src/pages/`: route-level composition and content loading

## Astro responsibilities

Astro should own:

- route files and page composition
- SEO metadata and document head
- static content, markdown, and CMS-fed sections
- layout primitives and shared wrappers
- section ordering and content choreography

Keep content-heavy UI in `.astro` files when it does not need client state.

## Svelte boundary rules

Reach for Svelte only when the component needs:

- client state that changes after load
- filtering, toggles, sorting, search, or local calculations
- animated state transitions that would be awkward in plain Astro
- form validation or progressive disclosure with keyboard interaction

Do not convert an entire page to Svelte when only one subsection is interactive.

## Hydration selection

Pick the lightest Astro directive that fits the behavior:

- `client:load`: above-the-fold interactions that must work immediately
- `client:visible`: below-the-fold widgets, accordions, galleries, comparison tools
- `client:idle`: non-critical enhancements after initial paint
- `client:media`: device-specific interaction that only matters at certain breakpoints

Default to `client:visible` when the component is not needed for first paint.

## Page scaffold

Use a small frontmatter block and keep page files declarative.

```astro
---
import BaseLayout from '../layouts/BaseLayout.astro';
import HeroSection from '../components/sections/HeroSection.astro';
import FeatureGrid from '../components/sections/FeatureGrid.astro';
import InteractivePanel from '../components/islands/InteractivePanel.svelte';
import '../styles/design-tokens.css';
---

<BaseLayout title="Product landing page">
  <HeroSection />
  <FeatureGrid />
  <InteractivePanel client:visible />
</BaseLayout>
```

## Content and styling guidance

- Move design tokens into shared CSS variables before writing one-off classes.
- Let each section have one dominant job: orient, prove, explain, convert, or reassure.
- Prefer a small set of reusable wrappers over deeply nested utility soup.
- Keep hero sections readable in plain HTML first, then layer polish.
- When imagery is absent, use shape, layout, and type contrast instead of fake screenshot boxes everywhere.

## Common section sequence shortcuts

- SaaS: hero -> proof -> features -> workflow -> pricing -> FAQ -> closing CTA
- service business: hero -> services -> process -> testimonials -> booking -> FAQ
- editorial: hero -> featured stories -> categories -> about/newsletter -> archive
- docs: hero/search -> quickstart -> core guides -> examples -> support links
