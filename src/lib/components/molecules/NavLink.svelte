<script lang="ts">
  import type { Snippet } from 'svelte';
  import { page } from '$app/stores';

  interface Props {
    href: string;
    variant?: 'default' | 'inverse';
    children: Snippet;
  }

  let { href, variant = 'default', children }: Props = $props();

  let isActive = $derived($page.url.pathname === href);
</script>

<a
  {href}
  class="nav-link"
  class:variant-default={variant === 'default'}
  class:variant-inverse={variant === 'inverse'}
  class:active={isActive}
  aria-current={isActive ? 'page' : undefined}
>
  {@render children()}
</a>

<style>
  .nav-link {
    position: relative;
    display: inline-flex;
    align-items: center;
    font-family: var(--font-body);
    font-size: var(--text-sm);
    font-weight: var(--weight-medium);
    text-decoration: none;
    transition: color var(--transition-fast);
  }

  .nav-link::after {
    content: '';
    position: absolute;
    bottom: -4px;
    left: 0;
    width: 0;
    height: 2px;
    background-color: var(--color-accent);
    transition: width var(--transition-base);
  }

  .nav-link:hover::after,
  .nav-link.active::after {
    width: 100%;
  }

  /* Default variant */
  .variant-default {
    color: var(--color-text-secondary);
  }

  .variant-default:hover,
  .variant-default.active {
    color: var(--color-text-primary);
  }

  /* Inverse variant */
  .variant-inverse {
    color: rgba(255, 255, 255, 0.7);
  }

  .variant-inverse:hover,
  .variant-inverse.active {
    color: var(--color-white);
  }
</style>
