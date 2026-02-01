<script lang="ts">
  import { Text } from '../atoms';

  interface Props {
    title: string;
    items: string[];
  }

  let { title, items }: Props = $props();
</script>

<div class="expertise-item">
  <h4 class="title">{title}</h4>
  <div class="items">
    {#each items as item}
      <Text variant="caption" color="secondary" as="span">{item}</Text>
    {/each}
  </div>
</div>

<style>
  .expertise-item {
    display: flex;
    flex-direction: column;
    gap: var(--space-2);
  }

  .title {
    font-family: var(--font-body);
    font-size: var(--text-base);
    font-weight: var(--weight-semibold);
    color: var(--color-text-primary);
    margin: 0;
  }

  .items {
    display: flex;
    flex-wrap: wrap;
    gap: var(--space-1) var(--space-3);
  }

  .items :global(span) {
    position: relative;
  }

  .items :global(span):not(:last-child)::after {
    content: '·';
    position: absolute;
    right: calc(-1 * var(--space-2));
    color: var(--color-gray-400);
  }
</style>
