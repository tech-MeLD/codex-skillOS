# Design Directions

## Brief inputs to extract

Pull these signals from the request before designing anything:

- audience and buying intent
- primary CTA and conversion moment
- trust requirement: low, medium, or high
- content density: sparse, medium, or heavy
- brand temperature: playful, neutral, premium, technical, or calm
- proof assets: testimonials, metrics, client logos, case studies, screenshots

If the user provides little brand guidance, infer one strong direction from the industry and state the assumption.

## Recommended page patterns

| Site type | Default section order | Notes |
| --- | --- | --- |
| SaaS landing page | Hero, proof bar, feature grid, workflow, pricing, FAQ, CTA footer | Lead with clarity, then prove speed and reliability |
| Service business | Hero, services, outcomes, testimonials, process, booking CTA, contact | Reassurance and booking friction matter more than novelty |
| Editorial or personal brand | Hero, featured stories, topic clusters, about, newsletter, footer | Typography and rhythm matter more than heavy motion |
| Product detail page | Hero, gallery, benefits, specs, comparison, FAQ, purchase CTA | Use contrast around pricing and technical details |
| Docs portal | Header, search, quickstarts, categories, examples, support links | Prioritize scanning and stable navigation |
| Lightweight dashboard | Page intro, summary cards, filters, charts, detail panel, export/help | Keep the frame calm and let data carry the visual weight |

## Style families

### Product Precision

Best for SaaS, AI tools, devtools, B2B products.

- palette: cool neutrals with one vivid accent
- type: geometric sans for UI, restrained display face only if the brand can carry it
- motion: short fades, directional slide-ins, no ornamental bounce
- layout: grid-forward, compact spacing, strong information grouping
- avoid: luxury serif headlines, oversized gradients, noisy shadow stacks

### Quiet Luxury

Best for boutique services, wellness, hospitality, interior design, premium brands.

- palette: warm neutrals, muted greens, clay, espresso, or metallic accent
- type: elegant serif plus disciplined sans
- motion: soft reveal, slow hover, gentle parallax only if performance stays strong
- layout: generous margins, fewer sections, strong photography support
- avoid: crypto colors, high-contrast dashboard widgets, neon accents

### Warm Minimal

Best for agencies, consultants, studios, local businesses, creator sites.

- palette: off-white base, one grounded dark, one warm accent
- type: humanist sans or low-contrast serif pairing
- motion: subtle underline, scale, and opacity transitions
- layout: roomy cards, obvious CTA hierarchy, minimal chrome
- avoid: cold enterprise blues everywhere, overbuilt nav, too many badges

### Editorial Contrast

Best for magazines, storytelling pages, portfolios, thought leadership.

- palette: paper-like backgrounds with one inky dark and one sharp highlight
- type: expressive display serif or grotesk headline paired with readable body text
- motion: restrained; use rhythm through spacing before animation
- layout: asymmetry, image blocks, quote pullouts, strong section breaks
- avoid: dashboard-like cards, excessive UI decoration, generic startup icons

### Playful Utility

Best for education, lifestyle products, family apps, community projects.

- palette: bright but curated, with one anchor neutral to prevent chaos
- type: rounded or friendly sans with strong size contrast
- motion: bouncy only in small touches; respect reduced motion
- layout: chunked content blocks, icon-led explanations, obvious affordances
- avoid: too many simultaneous accent colors, glassmorphism, dense tables

## Token defaults

Use these as a baseline when the brief is vague:

- spacing scale: 4, 8, 12, 16, 24, 32, 48, 64, 96
- radius scale: 10, 16, 24, 32
- border width: 1px for quiet surfaces, 1.5px to 2px for emphasized cards
- shadow policy: one soft elevation system, not stacked unrelated shadows
- motion timing: 140ms to 220ms for UI actions, 260ms to 420ms for reveal sequences

## Industry anti-patterns

- SaaS: avoid generic "AI purple" palettes and giant empty hero regions with no proof.
- Finance or security: avoid playful motion that weakens trust; let typography and structure carry authority.
- Wellness or beauty: avoid cold grayscale dashboards unless the brand is explicitly clinical.
- Food or hospitality: avoid thin, low-contrast body text and sterile card grids.
- Editorial: avoid overusing carousels and collapsible content that hides the story.
- Dashboards: avoid marketing-site gradients behind dense data views.
