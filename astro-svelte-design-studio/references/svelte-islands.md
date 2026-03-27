# Svelte Islands

## Use Svelte for the right problems

Choose a Svelte island when a section benefits from local state, user input, or richer keyboard interaction.

Good fits:

- pricing or billing toggle
- feature comparison switcher
- tabbed content panel
- FAQ accordion with search or grouping
- quiz, estimator, calculator, configurator
- filterable card or case-study grid
- nav state for mobile menus or section highlighting

Bad fits:

- static hero copy
- one-off hover animation
- decorative counters that could render statically
- full-page wrappers with no real client behavior

## Svelte 5 defaults

Prefer runes-based Svelte 5 patterns.

```svelte
<script lang="ts">
  type Tab = { label: string; title: string; body: string };

  let { items = [] as Tab[] } = $props();
  let activeIndex = $state(0);
  let activeItem = $derived(items[activeIndex]);
</script>
```

Guidelines:

- use `$props()` for inputs
- use `$state()` for mutable client state
- use `$derived()` for computed state
- use `$effect()` only for DOM or browser side effects
- keep business logic small; move heavy transforms to TypeScript helpers if needed

## Island design rules

- Keep the visual language consistent with the Astro shell; islands should feel embedded, not like mini-apps.
- Accept serializable props from Astro and avoid hidden global state when possible.
- Design the no-JS fallback experience first for forms, pricing, and FAQ content.
- Preserve focus when panels, menus, or disclosures change.
- Respect `prefers-reduced-motion` for animated widgets.

## Styling guidance

- Reuse CSS variables from the shared token file.
- Keep hover, focus, and active states visibly distinct.
- Use animation to clarify state change, not to decorate every click.
- Prefer layout stability over flourish; avoid UI that shifts height unexpectedly unless the pattern calls for disclosure.

## Suggested island starter ideas

- `InteractivePanel.svelte`: tabs or segmented content
- `PricingToggle.svelte`: monthly versus yearly plans
- `FilterGrid.svelte`: card filtering by category or persona
- `FaqAccordion.svelte`: searchable or grouped disclosures
- `LeadForm.svelte`: richer validation layered onto a plain form
