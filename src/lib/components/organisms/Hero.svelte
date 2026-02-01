<script lang="ts">
  import type { Snippet } from 'svelte';
  import { Logo, Heading, Text, Button } from '../atoms';

  interface Props {
    overline?: string;
    title: string;
    titleHighlight?: string;
    subtitle?: string;
    variant?: 'default' | 'centered' | 'split';
    showLogo?: boolean;
    ctaLabel?: string;
    ctaHref?: string;
    children?: Snippet;
  }

  let {
    overline,
    title,
    titleHighlight,
    subtitle,
    variant = 'default',
    showLogo = false,
    ctaLabel,
    ctaHref,
    children,
  }: Props = $props();
</script>

<section
  class="hero"
  class:variant-default={variant === 'default'}
  class:variant-centered={variant === 'centered'}
  class:variant-split={variant === 'split'}
>
  <div class="hero-background">
    <div class="gradient-overlay"></div>
  </div>

  <div class="hero-container">
    <div class="hero-content">
      {#if showLogo}
        <div class="hero-logo">
          <Logo size="xl" animated />
        </div>
      {/if}

      {#if overline}
        <Text variant="overline" color="accent">{overline}</Text>
      {/if}

      <Heading level={1} color="inverse" align={variant === 'centered' ? 'center' : 'left'}>
        {title}
        {#if titleHighlight}
          <span class="title-highlight">{titleHighlight}</span>
        {/if}
      </Heading>

      {#if subtitle}
        <Text variant="lead" color="inverse" align={variant === 'centered' ? 'center' : 'left'}>
          {subtitle}
        </Text>
      {/if}

      {#if ctaLabel && ctaHref}
        <div class="hero-cta">
          <Button variant="primary" size="lg" href={ctaHref}>
            {ctaLabel}
          </Button>
        </div>
      {/if}

      {#if children}
        <div class="hero-extra">
          {@render children()}
        </div>
      {/if}
    </div>
  </div>
</section>

<style>
  .hero {
    position: relative;
    min-height: 70vh;
    display: flex;
    align-items: center;
    overflow: hidden;
  }

  .hero-background {
    position: absolute;
    inset: 0;
    background-color: var(--color-primary);
    z-index: var(--z-behind);
  }

  .gradient-overlay {
    position: absolute;
    inset: 0;
    background:
      radial-gradient(ellipse at 20% 50%, rgba(201, 162, 39, 0.15) 0%, transparent 50%),
      radial-gradient(ellipse at 80% 80%, rgba(22, 33, 62, 0.8) 0%, transparent 50%);
  }

  .hero-container {
    width: 100%;
    max-width: var(--container-xl);
    margin-inline: auto;
    padding: var(--section-padding-y) var(--container-padding);
  }

  .hero-content {
    display: flex;
    flex-direction: column;
    gap: var(--space-6);
    max-width: 720px;
  }

  /* Variants */
  .variant-centered .hero-content {
    align-items: center;
    text-align: center;
    margin-inline: auto;
  }

  .variant-split .hero-content {
    max-width: 50%;
  }

  @media (max-width: 768px) {
    .variant-split .hero-content {
      max-width: 100%;
    }
  }

  /* Logo */
  .hero-logo {
    margin-bottom: var(--space-4);
  }

  .variant-centered .hero-logo {
    margin-inline: auto;
  }

  /* Title highlight */
  .title-highlight {
    display: block;
    color: var(--color-accent);
  }

  /* CTA */
  .hero-cta {
    margin-top: var(--space-4);
  }

  /* Extra content */
  .hero-extra {
    margin-top: var(--space-8);
  }

  /* Lead text styling for inverse */
  .hero-content :global(.text-lead) {
    opacity: 0.85;
  }
</style>
