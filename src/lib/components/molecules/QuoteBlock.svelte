<script lang="ts">
  interface Props {
    quote: string;
    variant?: 'default' | 'centered' | 'accent';
  }

  let { quote, variant = 'default' }: Props = $props();
</script>

<blockquote
  class="quote-block"
  class:variant-default={variant === 'default'}
  class:variant-centered={variant === 'centered'}
  class:variant-accent={variant === 'accent'}
>
  <p class="quote-text">{quote}</p>
</blockquote>

<style>
  .quote-block {
    margin: 0;
    padding: var(--space-6) 0;
  }

  .quote-text {
    font-family: var(--font-display);
    font-size: var(--text-2xl);
    font-style: italic;
    line-height: var(--leading-relaxed);
    margin: 0;
  }

  /* Variants */
  .variant-default {
    border-left: 3px solid var(--color-accent);
    padding-left: var(--space-6);
  }

  .variant-default .quote-text {
    color: var(--color-text-secondary);
  }

  .variant-centered {
    text-align: center;
    max-width: 700px;
    margin-inline: auto;
  }

  .variant-centered .quote-text {
    color: var(--color-text-secondary);
  }

  .variant-accent .quote-text {
    color: var(--color-accent);
  }
</style>
