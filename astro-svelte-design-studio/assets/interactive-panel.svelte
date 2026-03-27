<script lang="ts">
  type PanelItem = {
    label: string;
    title: string;
    body: string;
    meta?: string;
  };

  let {
    heading = 'Explore the system',
    items = [] as PanelItem[],
  } = $props<{
    heading?: string;
    items?: PanelItem[];
  }>();

  let activeIndex = $state(0);
  let activeItem = $derived(items[activeIndex] ?? { label: '', title: '', body: '', meta: '' });
</script>

<section class="panel surface-card" aria-label={heading}>
  <div class="panel__header">
    <p class="eyebrow">Svelte island</p>
    <h2>{heading}</h2>
  </div>

  <div class="panel__tabs" role="tablist" aria-label={heading}>
    {#each items as item, index}
      <button
        type="button"
        class:panel__tab--active={index === activeIndex}
        class="panel__tab"
        role="tab"
        aria-selected={index === activeIndex}
        onclick={() => (activeIndex = index)}
      >
        {item.label}
      </button>
    {/each}
  </div>

  <article class="panel__body" role="tabpanel">
    <p class="panel__meta">{activeItem.meta}</p>
    <h3>{activeItem.title}</h3>
    <p>{activeItem.body}</p>
  </article>
</section>

<style>
  .panel {
    padding: var(--space-6);
  }

  .panel__header h2 {
    margin: var(--space-3) 0 0;
    font-family: var(--font-display);
    font-size: clamp(1.6rem, 4vw, 2.4rem);
    line-height: 1;
  }

  .panel__tabs {
    display: flex;
    flex-wrap: wrap;
    gap: var(--space-2);
    margin: var(--space-6) 0;
  }

  .panel__tab {
    min-height: 2.7rem;
    padding: 0.7rem 1rem;
    border: 1px solid var(--color-line);
    border-radius: var(--radius-pill);
    background: transparent;
    color: var(--color-text);
    font: inherit;
    cursor: pointer;
    transition:
      transform var(--transition-fast),
      border-color var(--transition-fast),
      background-color var(--transition-fast),
      color var(--transition-fast);
  }

  .panel__tab:hover,
  .panel__tab:focus-visible {
    border-color: rgba(36, 31, 26, 0.28);
    transform: translateY(-1px);
    outline: none;
  }

  .panel__tab:focus-visible {
    box-shadow: 0 0 0 3px rgba(184, 92, 56, 0.2);
  }

  .panel__tab--active {
    background: var(--color-text);
    border-color: var(--color-text);
    color: white;
  }

  .panel__body {
    border-top: 1px solid var(--color-line);
    padding-top: var(--space-6);
  }

  .panel__meta {
    margin: 0;
    color: var(--color-text-muted);
    font-size: 0.9rem;
    letter-spacing: 0.03em;
    text-transform: uppercase;
  }

  .panel__body h3 {
    margin: var(--space-3) 0;
    font-family: var(--font-display);
    font-size: clamp(1.35rem, 3vw, 1.9rem);
    line-height: 1.1;
  }

  .panel__body p:last-child {
    margin: 0;
    color: var(--color-text-muted);
    line-height: 1.7;
  }
</style>
