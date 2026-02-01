<script lang="ts">
  import type { Snippet } from 'svelte';

  interface Props {
    variant?: 'default' | 'accent' | 'outline';
    size?: 'sm' | 'md';
    children: Snippet;
  }

  let { variant = 'default', size = 'md', children }: Props = $props();
</script>

<span
  class="badge"
  class:variant-default={variant === 'default'}
  class:variant-accent={variant === 'accent'}
  class:variant-outline={variant === 'outline'}
  class:size-sm={size === 'sm'}
  class:size-md={size === 'md'}
>
  {@render children()}
</span>

<style>
  .badge {
    display: inline-flex;
    align-items: center;
    justify-content: center;
    font-family: var(--font-body);
    font-weight: var(--weight-medium);
    white-space: nowrap;
    border-radius: var(--radius-full);
  }

  /* Sizes */
  .size-sm {
    padding: var(--space-1) var(--space-2);
    font-size: var(--text-xs);
  }

  .size-md {
    padding: var(--space-1) var(--space-3);
    font-size: var(--text-sm);
  }

  /* Variants */
  .variant-default {
    background-color: var(--color-gray-100);
    color: var(--color-text-secondary);
  }

  .variant-accent {
    background-color: var(--color-accent-muted);
    color: var(--color-accent-dark);
  }

  .variant-outline {
    background-color: transparent;
    color: var(--color-text-secondary);
    border: 1px solid var(--color-border);
  }
</style>
