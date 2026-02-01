<script lang="ts">
  import type { Snippet } from 'svelte';

  interface Props {
    variant?: 'default' | 'elevated' | 'outlined' | 'filled';
    padding?: 'sm' | 'md' | 'lg';
    hoverable?: boolean;
    children: Snippet;
  }

  let { variant = 'default', padding = 'md', hoverable = false, children }: Props = $props();
</script>

<article
  class="card"
  class:variant-default={variant === 'default'}
  class:variant-elevated={variant === 'elevated'}
  class:variant-outlined={variant === 'outlined'}
  class:variant-filled={variant === 'filled'}
  class:padding-sm={padding === 'sm'}
  class:padding-md={padding === 'md'}
  class:padding-lg={padding === 'lg'}
  class:hoverable
>
  {@render children()}
</article>

<style>
  .card {
    border-radius: var(--radius-xl);
    transition:
      transform var(--transition-base),
      box-shadow var(--transition-base);
  }

  /* Padding */
  .padding-sm {
    padding: var(--space-4);
  }
  .padding-md {
    padding: var(--space-6);
  }
  .padding-lg {
    padding: var(--space-8);
  }

  /* Variants */
  .variant-default {
    background-color: var(--color-bg-primary);
  }

  .variant-elevated {
    background-color: var(--color-bg-primary);
    box-shadow: var(--shadow-md);
  }

  .variant-outlined {
    background-color: var(--color-bg-primary);
    border: var(--border-width) solid var(--color-border);
  }

  .variant-filled {
    background-color: var(--color-bg-secondary);
  }

  /* Hover */
  .hoverable {
    cursor: pointer;
  }

  .hoverable:hover {
    transform: translateY(-4px);
  }

  .hoverable.variant-elevated:hover {
    box-shadow: var(--shadow-xl);
  }

  .hoverable.variant-outlined:hover {
    border-color: var(--color-accent);
  }

  .hoverable.variant-filled:hover {
    background-color: var(--color-gray-100);
  }
</style>
