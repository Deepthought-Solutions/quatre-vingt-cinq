<script lang="ts">
  import { SectionHeader, EngagementItem, QuoteBlock } from '../molecules';

  interface Props {
    overline?: string;
    title?: string;
    subtitle?: string;
    engagements: string[];
    quote?: string;
  }

  let {
    overline = 'Nos engagements',
    title = 'Indépendants par choix. Engagés par conviction.',
    subtitle,
    engagements,
    quote,
  }: Props = $props();
</script>

<section class="engagements-section">
  <div class="container">
    <div class="content-grid">
      <div class="header-column">
        <SectionHeader {overline} {title} {subtitle} />
      </div>

      <div class="engagements-column">
        <ul class="engagements-list">
          {#each engagements as engagement}
            <li>
              <EngagementItem text={engagement} />
            </li>
          {/each}
        </ul>
      </div>
    </div>

    {#if quote}
      <div class="quote-wrapper">
        <QuoteBlock {quote} variant="accent" />
      </div>
    {/if}
  </div>
</section>

<style>
  .engagements-section {
    padding-block: var(--section-padding-y);
  }

  .container {
    max-width: var(--container-xl);
    margin-inline: auto;
    padding-inline: var(--container-padding);
  }

  .content-grid {
    display: grid;
    gap: var(--space-12);
  }

  @media (min-width: 768px) {
    .content-grid {
      grid-template-columns: 1fr 1fr;
      gap: var(--space-16);
      align-items: start;
    }
  }

  .header-column {
    position: sticky;
    top: calc(var(--space-20));
  }

  .engagements-list {
    display: flex;
    flex-direction: column;
    gap: var(--space-6);
    list-style: none;
    margin: 0;
    padding: 0;
  }

  .quote-wrapper {
    margin-top: var(--space-16);
    padding-top: var(--space-8);
    border-top: 1px solid var(--color-border);
    max-width: 700px;
  }
</style>
