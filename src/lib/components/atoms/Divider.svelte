<script lang="ts">
  interface Props {
    variant?: 'solid' | 'accent' | 'gradient';
    spacing?: 'sm' | 'md' | 'lg';
    orientation?: 'horizontal' | 'vertical';
  }

  let { variant = 'solid', spacing = 'md', orientation = 'horizontal' }: Props = $props();
</script>

<div
  class="divider"
  class:variant-solid={variant === 'solid'}
  class:variant-accent={variant === 'accent'}
  class:variant-gradient={variant === 'gradient'}
  class:spacing-sm={spacing === 'sm'}
  class:spacing-md={spacing === 'md'}
  class:spacing-lg={spacing === 'lg'}
  class:horizontal={orientation === 'horizontal'}
  class:vertical={orientation === 'vertical'}
  role="separator"
  aria-orientation={orientation}
></div>

<style>
  .divider {
    flex-shrink: 0;
  }

  .horizontal {
    width: 100%;
    height: 1px;
  }

  .vertical {
    width: 1px;
    height: 100%;
  }

  /* Spacing */
  .horizontal.spacing-sm {
    margin-block: var(--space-4);
  }
  .horizontal.spacing-md {
    margin-block: var(--space-8);
  }
  .horizontal.spacing-lg {
    margin-block: var(--space-12);
  }

  .vertical.spacing-sm {
    margin-inline: var(--space-4);
  }
  .vertical.spacing-md {
    margin-inline: var(--space-8);
  }
  .vertical.spacing-lg {
    margin-inline: var(--space-12);
  }

  /* Variants */
  .variant-solid {
    background-color: var(--color-border);
  }

  .variant-accent {
    background-color: var(--color-accent);
  }

  .variant-gradient {
    background: linear-gradient(90deg, transparent 0%, var(--color-accent) 50%, transparent 100%);
  }

  .vertical.variant-gradient {
    background: linear-gradient(180deg, transparent 0%, var(--color-accent) 50%, transparent 100%);
  }
</style>
