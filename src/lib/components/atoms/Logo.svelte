<script lang="ts">
  import { base } from '$app/paths';

  interface Props {
    size?: 'sm' | 'md' | 'lg' | 'xl';
    animated?: boolean;
  }

  let { size = 'md', animated = false }: Props = $props();

  const heights = {
    sm: '2rem',
    md: '3rem',
    lg: '4.5rem',
    xl: '6rem',
  };
</script>

<div class="logo" class:animated style="--logo-height: {heights[size]}">
  <img src="{base}/logo_85.jpeg" alt="85 Conseil et Recrutement" class="logo-img" />
</div>

<style>
  .logo {
    display: inline-flex;
    align-items: center;
  }

  .logo-img {
    height: var(--logo-height);
    width: auto;
    object-fit: contain;
    filter: grayscale(100%) contrast(1.2);
  }

  .animated {
    animation: pulse 3s ease-in-out infinite;
  }

  @keyframes pulse {
    0%,
    100% {
      filter: grayscale(100%) contrast(1.2);
    }
    50% {
      filter: grayscale(100%) contrast(1.2) drop-shadow(0 0 8px rgba(201, 162, 39, 0.4));
    }
  }
</style>
