---
name: astro-svelte-design-studio
description: Website design and implementation guidance for Astro projects that use Svelte islands. Use when Codex needs to design, prototype, build, or refine landing pages, marketing sites, editorial sites, product pages, docs portals, or lightweight dashboards in Astro with Svelte-powered interactivity. Trigger for visual direction, design systems, responsive layouts, section planning, component styling, motion, accessibility, and Astro/Svelte-specific architecture tradeoffs.
---

# Astro Svelte Design Studio

## Overview

Design websites with a static-first Astro architecture and selective Svelte islands. Start from the product brief, turn it into a focused design system, map that system to page sections, then implement only the interactivity that materially improves the experience.

Support Astro and Svelte only. If the request is primarily for React, Next.js, Vue, Nuxt, or a full SPA, do not force this skill's patterns onto it.

## Core Workflow

1. Distill the brief into audience, promise, CTA, trust signals, and content density.
2. Choose one visual direction instead of mixing multiple aesthetics.
3. Produce a compact design system: color roles, typography, spacing, radii, shadows, borders, and motion.
4. Choose a page pattern that fits the business goal and reading flow.
5. Keep Astro responsible for shells, layout, content sections, SEO, and data loading.
6. Use Svelte only for islands such as tabs, calculators, filters, pricing toggles, accordions, comparison tools, and progressive disclosure.
7. Validate responsiveness, accessibility, and performance before finishing.

## Non-Negotiables

- Prefer static-first composition. Hydrate only the pieces that need state, input, animation coordination, or live filtering.
- Keep the number of islands low and purposeful. One strong interaction is better than five decorative ones.
- Use CSS variables for tokens and reuse them across `.astro`, `.svelte`, and global styles.
- Match layout, colors, and motion to the user's industry. Avoid generic AI gradients, random glassmorphism, and template-looking sections unless the brief explicitly calls for them.
- Design mobile first, then expand to tablet and desktop with intentional spacing and hierarchy changes.
- Favor semantic HTML, visible focus states, and contrast that survives light backgrounds.
- Prefer short implementation notes plus concrete edits over abstract design theory.

## Resource Map

- Read `references/design-directions.md` when choosing style families, palettes, section structures, or industry-specific anti-patterns.
- Read `references/astro-patterns.md` when deciding page architecture, section composition, routing, or how to structure Astro files.
- Read `references/svelte-islands.md` when deciding whether an interaction should be a Svelte island and how to implement it cleanly.
- Read `references/delivery-checklist.md` before shipping or reviewing a page.
- Reuse `assets/page-shell.astro` for a static-first page scaffold.
- Reuse `assets/interactive-panel.svelte` for a Svelte 5 island pattern.
- Reuse `assets/design-tokens.css` for a starting token system.

## Delivery Pattern

When the request is open-ended, provide or implement work in this order:

1. Design direction in 4-8 lines.
2. Page outline with section order and CTA placement.
3. Token choices for color, type, spacing, radius, and motion.
4. Astro/Svelte boundary decisions.
5. Code edits or starter files.
6. Final QA against the checklist.

## Default Build Heuristics

- Marketing and editorial pages: mostly Astro, with Svelte for navigation state, tabs, carousels only if justified, and forms that need richer behavior.
- Product comparison, calculators, pricing selectors, FAQ search, filter panels: use Svelte islands with clear props and narrow hydration.
- Long-form content pages: let Astro own the content and use Svelte only for enhancements, never the entire reading experience.
- If content is missing, infer a plausible tone and structure from the industry and clearly state assumptions in the response or commit message.
