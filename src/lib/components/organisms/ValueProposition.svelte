<script lang="ts">
  import { Text } from '../atoms';
  import { Card } from '../molecules';

  interface ValueItem {
    title: string;
    description: string;
  }

  interface Props {
    items: ValueItem[];
  }

  let { items }: Props = $props();
</script>

<section class="value-section">
  <div class="container">
    <div class="value-grid">
      {#each items as item}
        <Card variant="filled" padding="lg">
          <div class="value-item">
            <h3 class="value-title">{item.title}</h3>
            <Text variant="body" color="secondary">{item.description}</Text>
          </div>
        </Card>
      {/each}
    </div>
  </div>
</section>

<style>
  .value-section {
    padding-block: var(--section-padding-y);
    background-color: var(--color-bg-primary);
  }

  .container {
    max-width: var(--container-xl);
    margin-inline: auto;
    padding-inline: var(--container-padding);
  }

  .value-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
    gap: var(--space-6);
  }

  .value-item {
    display: flex;
    flex-direction: column;
    gap: var(--space-3);
  }

  .value-title {
    font-family: var(--font-display);
    font-size: var(--text-xl);
    font-weight: var(--weight-semibold);
    color: var(--color-text-primary);
    margin: 0;
  }
</style>
