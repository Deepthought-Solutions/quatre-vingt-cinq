<script lang="ts">
  import type { Snippet } from 'svelte';

  interface Props {
    level?: 1 | 2 | 3 | 4 | 5 | 6;
    as?: 'h1' | 'h2' | 'h3' | 'h4' | 'h5' | 'h6' | 'p' | 'span';
    color?: 'primary' | 'secondary' | 'accent' | 'inverse';
    align?: 'left' | 'center' | 'right';
    children: Snippet;
  }

  let { level = 2, as, color = 'primary', align = 'left', children }: Props = $props();

  let tag = $derived(as ?? `h${level}`);
</script>

<svelte:element
  this={tag}
  class="heading heading-{level}"
  class:color-primary={color === 'primary'}
  class:color-secondary={color === 'secondary'}
  class:color-accent={color === 'accent'}
  class:color-inverse={color === 'inverse'}
  class:align-left={align === 'left'}
  class:align-center={align === 'center'}
  class:align-right={align === 'right'}
>
  {@render children()}
</svelte:element>

<style>
  .heading {
    margin: 0;
    font-family: var(--font-display);
    line-height: var(--leading-tight);
    letter-spacing: var(--tracking-tight);
  }

  .heading-1 {
    font-size: var(--text-6xl);
    font-weight: var(--weight-semibold);
    line-height: var(--leading-none);
  }

  .heading-2 {
    font-size: var(--text-5xl);
    font-weight: var(--weight-semibold);
  }

  .heading-3 {
    font-size: var(--text-4xl);
    font-weight: var(--weight-medium);
  }

  .heading-4 {
    font-size: var(--text-3xl);
    font-weight: var(--weight-medium);
  }

  .heading-5 {
    font-family: var(--font-body);
    font-size: var(--text-2xl);
    font-weight: var(--weight-semibold);
    letter-spacing: var(--tracking-normal);
  }

  .heading-6 {
    font-family: var(--font-body);
    font-size: var(--text-xl);
    font-weight: var(--weight-semibold);
    letter-spacing: var(--tracking-normal);
  }

  .color-primary {
    color: var(--color-text-primary);
  }
  .color-secondary {
    color: var(--color-text-secondary);
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
