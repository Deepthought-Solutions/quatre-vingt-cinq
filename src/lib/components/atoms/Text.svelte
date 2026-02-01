<script lang="ts">
  import type { Snippet } from 'svelte';

  interface Props {
    variant?: 'body' | 'body-sm' | 'body-lg' | 'lead' | 'quote' | 'caption' | 'overline';
    color?: 'primary' | 'secondary' | 'muted' | 'accent' | 'inverse';
    align?: 'left' | 'center' | 'right';
    as?: 'p' | 'span' | 'div';
    children: Snippet;
  }

  let { variant = 'body', color = 'primary', align = 'left', as = 'p', children }: Props = $props();
</script>

<svelte:element
  this={as}
  class="text text-{variant}"
  class:color-primary={color === 'primary'}
  class:color-secondary={color === 'secondary'}
  class:color-muted={color === 'muted'}
  class:color-accent={color === 'accent'}
  class:color-inverse={color === 'inverse'}
  class:align-left={align === 'left'}
  class:align-center={align === 'center'}
  class:align-right={align === 'right'}
>
  {@render children()}
</svelte:element>

<style>
  .text {
    margin: 0;
    font-family: var(--font-body);
  }

  .text-body {
    font-size: var(--text-base);
    line-height: var(--leading-relaxed);
  }

  .text-body-sm {
    font-size: var(--text-sm);
    line-height: var(--leading-relaxed);
  }

  .text-body-lg {
    font-size: var(--text-lg);
    line-height: var(--leading-relaxed);
  }

  .text-lead {
    font-size: var(--text-xl);
    line-height: var(--leading-relaxed);
  }

  .text-quote {
    font-family: var(--font-display);
    font-size: var(--text-2xl);
    font-style: italic;
    line-height: var(--leading-relaxed);
  }

  .text-caption {
    font-size: var(--text-sm);
    line-height: var(--leading-normal);
  }

  .text-overline {
    font-size: var(--text-xs);
    font-weight: var(--weight-semibold);
    letter-spacing: var(--tracking-widest);
    text-transform: uppercase;
  }

  .color-primary {
    color: var(--color-text-primary);
  }
  .color-secondary {
    color: var(--color-text-secondary);
  }
  .color-muted {
    color: var(--color-text-muted);
  }
  .color-accent {
    color: var(--color-accent);
  }
  .color-inverse {
    color: var(--color-text-inverse);
  }

  .align-left {
    text-align: left;
  }
  .align-center {
    text-align: center;
  }
  .align-right {
    text-align: right;
  }
</style>
