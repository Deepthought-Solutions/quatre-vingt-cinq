<script lang="ts">
  import type { Snippet } from 'svelte';

  interface Props {
    variant?: 'primary' | 'secondary' | 'outline' | 'ghost';
    size?: 'sm' | 'md' | 'lg';
    href?: string;
    disabled?: boolean;
    fullWidth?: boolean;
    children: Snippet;
    type?: 'button' | 'submit' | 'reset';
    onclick?: (_event: MouseEvent) => void;
  }

  let {
    variant = 'primary',
    size = 'md',
    href,
    disabled = false,
    fullWidth = false,
    children,
    type = 'button',
    onclick,
  }: Props = $props();

  let classes = $derived(
    ['button', `variant-${variant}`, `size-${size}`, fullWidth ? 'full-width' : '']
      .filter(Boolean)
      .join(' ')
  );
</script>

{#if href}
  <a {href} class={classes} aria-disabled={disabled || undefined}>
    {@render children()}
  </a>
{:else}
  <button class={classes} {disabled} {onclick} {type}>
    {@render children()}
  </button>
{/if}

<style>
  .button {
    display: inline-flex;
    align-items: center;
    justify-content: center;
    gap: var(--space-2);
    font-family: var(--font-body);
    font-weight: var(--weight-medium);
    text-decoration: none;
    border-radius: var(--radius-md);
    cursor: pointer;
    transition:
      background-color var(--transition-fast),
      color var(--transition-fast),
      border-color var(--transition-fast),
      box-shadow var(--transition-fast),
      transform var(--transition-fast);
  }

  .button:disabled,
  .button[aria-disabled='true'] {
    opacity: 0.5;
    cursor: not-allowed;
    pointer-events: none;
  }

  /* Sizes */
  .size-sm {
    padding: var(--space-2) var(--space-4);
    font-size: var(--text-sm);
  }

  .size-md {
    padding: var(--space-3) var(--space-6);
    font-size: var(--text-base);
  }

  .size-lg {
    padding: var(--space-4) var(--space-8);
    font-size: var(--text-lg);
  }

  /* Variants */
  .variant-primary {
    background-color: var(--color-accent);
    color: var(--color-white);
    border: var(--border-width-2) solid var(--color-accent);
  }

  .variant-primary:hover:not(:disabled):not([aria-disabled='true']) {
    background-color: var(--color-accent-dark);
    border-color: var(--color-accent-dark);
    box-shadow: var(--shadow-accent);
  }

  .variant-primary:active:not(:disabled):not([aria-disabled='true']) {
    transform: translateY(1px);
  }

  .variant-secondary {
    background-color: var(--color-primary);
    color: var(--color-white);
    border: var(--border-width-2) solid var(--color-primary);
  }

  .variant-secondary:hover:not(:disabled):not([aria-disabled='true']) {
    background-color: var(--color-primary-light);
    border-color: var(--color-primary-light);
  }

  .variant-outline {
    background-color: transparent;
    color: var(--color-accent);
    border: var(--border-width-2) solid var(--color-accent);
  }

  .variant-outline:hover:not(:disabled):not([aria-disabled='true']) {
    background-color: var(--color-accent);
    color: var(--color-white);
  }

  .variant-ghost {
    background-color: transparent;
    color: var(--color-text-primary);
    border: var(--border-width-2) solid transparent;
  }

  .variant-ghost:hover:not(:disabled):not([aria-disabled='true']) {
    background-color: var(--color-gray-100);
  }

  .full-width {
    width: 100%;
  }
</style>
