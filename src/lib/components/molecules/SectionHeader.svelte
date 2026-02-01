<script lang="ts">
  import type { Snippet } from 'svelte';
  import { Heading, Text } from '../atoms';

  interface Props {
    overline?: string;
    title: string;
    subtitle?: string;
    align?: 'left' | 'center';
    titleColor?: 'primary' | 'accent' | 'inverse';
    children?: Snippet;
  }

  let {
    overline,
    title,
    subtitle,
    align = 'left',
    titleColor = 'primary',
    children,
  }: Props = $props();
</script>

<header class="section-header" class:align-center={align === 'center'}>
  {#if overline}
    <Text variant="overline" color="accent">{overline}</Text>
  {/if}

  <Heading level={2} color={titleColor} {align}>
    {title}
  </Heading>

  {#if subtitle}
    <Text variant="lead" color="secondary" {align}>
      {subtitle}
    </Text>
  {/if}

  {#if children}
    {@render children()}
  {/if}
</header>

<style>
  .section-header {
    display: flex;
    flex-direction: column;
    gap: var(--space-4);
    max-width: 720px;
  }

  .align-center {
    align-items: center;
    text-align: center;
    margin-inline: auto;
  }
</style>
