<script lang="ts">
  import { SectionHeader, ExpertiseItem, Card } from '../molecules';

  interface Expertise {
    title: string;
    items: string[];
  }

  interface Props {
    title?: string;
    subtitle?: string;
    expertises: Expertise[];
  }

  let { title = "Domaines d'intervention", subtitle, expertises }: Props = $props();
</script>

<section class="expertise-section">
  <div class="container">
    <SectionHeader {title} {subtitle} align="center" />

    <div class="expertise-grid">
      {#each expertises as expertise}
        <Card variant="outlined" padding="md" hoverable>
          <ExpertiseItem title={expertise.title} items={expertise.items} />
        </Card>
      {/each}
    </div>

    <div class="location-badge">
      <span class="location-text">Centre-Val de Loire · Île-de-France · National</span>
    </div>
  </div>
</section>

<style>
  .expertise-section {
    padding-block: var(--section-padding-y);
  }

  .container {
    max-width: var(--container-xl);
    margin-inline: auto;
    padding-inline: var(--container-padding);
  }

  .expertise-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
    gap: var(--space-6);
    margin-top: var(--space-12);
  }

  .location-badge {
    display: flex;
    justify-content: center;
    margin-top: var(--space-12);
  }

  .location-text {
    font-family: var(--font-body);
    font-size: var(--text-sm);
    color: var(--color-text-muted);
    background-color: var(--color-bg-secondary);
    padding: var(--space-2) var(--space-4);
    border-radius: var(--radius-full);
  }
</style>
