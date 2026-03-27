# Custom Skill Library

A focused skill library for AI coding agents, tailored around practical workflows instead of generic prompt dumps.

## Included skills

- `astro-svelte-design-studio`: Design and build polished websites in Astro with Svelte islands.
- `openai-docs`: Official OpenAI product and API documentation helper.
- `skill-creator`: Scaffolding and validation for creating new skills.
- `skill-installer`: Install curated skills or skills from GitHub.

## Repository shape

Each top-level skill folder is self-contained and follows the same layout:

- `SKILL.md`: trigger metadata plus workflow instructions.
- `agents/openai.yaml`: UI-facing metadata for invocation chips.
- `references/`: deep guidance loaded only when needed.
- `assets/`: starter files and templates reused in generated work.

## Featured skill

`astro-svelte-design-studio` is a custom website design skill, but narrowed to one stack: Astro for static-first pages and Svelte for selective interactive islands.

# codex-skillOS

A structured skill library for AI agents and automation.