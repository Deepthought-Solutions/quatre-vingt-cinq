<script lang="ts">
  import { SectionHeader, MethodStep, QuoteBlock } from '../molecules';

  interface Step {
    title: string;
    description: string;
  }

  interface Props {
    overline?: string;
    title?: string;
    subtitle?: string;
    steps: Step[];
    quote?: string;
  }

  let {
    overline = 'Notre méthode',
    title = 'Une chasse artisanale, directe et confidentielle',
    subtitle,
    steps,
    quote,
  }: Props = $props();
</script>

<section class="method-section">
  <div class="container">
    <SectionHeader {overline} {title} {subtitle} />

    <div class="steps-list">
      {#each steps as step, index}
        <MethodStep number={index + 1} title={step.title} description={step.description} />
      {/each}
    </div>

    {#if quote}
      <div class="quote-wrapper">
        <QuoteBlock {quote} variant="centered" />
      </div>
    {/if}
  </div>
</section>

<style>
  .method-section {
    padding-block: var(--section-padding-y);
    background-color: var(--color-bg-secondary);
  }

  .container {
    max-width: var(--container-lg);
    margin-inline: auto;
    padding-inline: var(--container-padding);
  }

  .steps-list {
    display: flex;
    flex-direction: column;
    gap: var(--space-8);
    margin-top: var(--space-12);
  }

  .quote-wrapper {
    margin-top: var(--space-16);
    padding-top: var(--space-8);
    border-top: 1px solid var(--color-border);
  }
</style>
