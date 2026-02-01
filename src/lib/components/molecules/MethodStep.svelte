<script lang="ts">
  import { Text } from '../atoms';

  interface Props {
    number?: number;
    title: string;
    description: string;
  }

  let { number, title, description }: Props = $props();
</script>

<div class="method-step">
  {#if number}
    <div class="number-badge">{number}</div>
  {/if}
  <div class="content">
    <h4 class="title">{title}</h4>
    <Text variant="body" color="secondary">{description}</Text>
  </div>
</div>

<style>
  .method-step {
    display: flex;
    gap: var(--space-4);
  }

  .number-badge {
    flex-shrink: 0;
    display: flex;
    align-items: center;
    justify-content: center;
    width: 2.5rem;
    height: 2.5rem;
    background-color: var(--color-accent-muted);
    color: var(--color-accent);
    font-family: var(--font-display);
    font-size: var(--text-lg);
    font-weight: var(--weight-semibold);
    border-radius: var(--radius-full);
  }

  .content {
    display: flex;
    flex-direction: column;
    gap: var(--space-2);
    padding-top: var(--space-1);
  }

  .title {
    font-family: var(--font-body);
    font-size: var(--text-lg);
    font-weight: var(--weight-semibold);
    color: var(--color-text-primary);
    margin: 0;
  }
</style>
