<script lang="ts">
  interface Props {
    text: string;
  }

  let { text }: Props = $props();
</script>

<div class="engagement-item">
  <div class="icon">
    <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
      <path d="M20 6L9 17l-5-5" stroke-linecap="round" stroke-linejoin="round" />
    </svg>
  </div>
  <span class="text">{text}</span>
</div>

<style>
  .engagement-item {
    display: flex;
    align-items: center;
    gap: var(--space-3);
  }

  .icon {
    flex-shrink: 0;
    width: 1.5rem;
    height: 1.5rem;
    color: var(--color-accent);
  }

  .icon svg {
    width: 100%;
    height: 100%;
  }

  .text {
    font-family: var(--font-body);
    font-size: var(--text-base);
    color: var(--color-text-primary);
  }
</style>
