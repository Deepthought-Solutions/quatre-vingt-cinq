<script lang="ts">
  interface Props {
    size?: 'sm' | 'md' | 'lg' | 'xl';
    animated?: boolean;
  }

  let { size = 'md', animated = false }: Props = $props();

  const sizes = {
    sm: '2rem',
    md: '3rem',
    lg: '4.5rem',
    xl: '6rem',
  };
</script>

<div class="logo" class:animated style="--logo-size: {sizes[size]}">
  <span class="logo-number">85</span>
</div>

<style>
  .logo {
    display: inline-flex;
    align-items: center;
    justify-content: center;
    width: var(--logo-size);
    height: var(--logo-size);
    background: linear-gradient(135deg, var(--color-accent) 0%, var(--color-accent-dark) 100%);
    border-radius: var(--radius-lg);
    box-shadow: var(--shadow-accent);
  }

  .logo-number {
    font-family: var(--font-display);
    font-size: calc(var(--logo-size) * 0.45);
    font-weight: var(--weight-bold);
    color: var(--color-white);
    letter-spacing: var(--tracking-tight);
  }

  .animated {
    animation: pulse 3s ease-in-out infinite;
  }

  @keyframes pulse {
    0%,
    100% {
      box-shadow: var(--shadow-accent);
    }
    50% {
      box-shadow: var(--shadow-accent-lg);
    }
  }
</style>
