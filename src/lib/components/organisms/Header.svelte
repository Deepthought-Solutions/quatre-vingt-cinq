<script lang="ts">
  import { Logo, Button } from '../atoms';
  import { NavLink } from '../molecules';

  interface NavItem {
    href: string;
    label: string;
  }

  interface Props {
    variant?: 'default' | 'transparent';
  }

  let { variant = 'default' }: Props = $props();

  const navigation: NavItem[] = [
    { href: '/', label: 'Expertise' },
    { href: '/methode', label: 'Notre méthode' },
    { href: '/qui-sommes-nous', label: 'Qui sommes-nous' },
  ];

  let mobileMenuOpen = $state(false);

  function toggleMobileMenu() {
    mobileMenuOpen = !mobileMenuOpen;
  }
</script>

<header
  class="header"
  class:variant-default={variant === 'default'}
  class:variant-transparent={variant === 'transparent'}
>
  <div class="header-container">
    <a href="/" class="logo-link" aria-label="85 Conseil & Recrutement - Accueil">
      <Logo size="sm" />
      <div class="logo-text">
        <span class="logo-name">85 Conseil</span>
        <span class="logo-tagline">Recrutement</span>
      </div>
    </a>

    <nav class="desktop-nav" aria-label="Navigation principale">
      {#each navigation as item}
        <NavLink href={item.href} variant={variant === 'transparent' ? 'inverse' : 'default'}>
          {item.label}
        </NavLink>
      {/each}
    </nav>

    <div class="header-actions">
      <Button
        variant={variant === 'transparent' ? 'outline' : 'primary'}
        size="sm"
        href="/#contact"
      >
        Contact
      </Button>
    </div>

    <button
      class="mobile-menu-toggle"
      class:open={mobileMenuOpen}
      onclick={toggleMobileMenu}
      aria-expanded={mobileMenuOpen}
      aria-controls="mobile-menu"
      aria-label={mobileMenuOpen ? 'Fermer le menu' : 'Ouvrir le menu'}
    >
      <span class="bar"></span>
      <span class="bar"></span>
      <span class="bar"></span>
    </button>
  </div>

  {#if mobileMenuOpen}
    <nav id="mobile-menu" class="mobile-nav" aria-label="Navigation mobile">
      {#each navigation as item}
        <a href={item.href} class="mobile-nav-link" onclick={() => (mobileMenuOpen = false)}>
          {item.label}
        </a>
      {/each}
      <Button variant="primary" size="sm" href="/#contact" fullWidth>Contact</Button>
    </nav>
  {/if}
</header>

<style>
  .header {
    position: sticky;
    top: 0;
    z-index: var(--z-sticky);
    transition: background-color var(--transition-base);
  }

  .variant-default {
    background-color: var(--color-bg-primary);
    border-bottom: 1px solid var(--color-border-light);
  }

  .variant-transparent {
    background-color: transparent;
  }

  .header-container {
    display: flex;
    align-items: center;
    justify-content: space-between;
    gap: var(--space-6);
    max-width: var(--container-xl);
    margin-inline: auto;
    padding: var(--space-4) var(--container-padding);
  }

  /* Logo */
  .logo-link {
    display: flex;
    align-items: center;
    gap: var(--space-3);
    text-decoration: none;
  }

  .logo-text {
    display: flex;
    flex-direction: column;
  }

  .logo-name {
    font-family: var(--font-display);
    font-size: var(--text-base);
    font-weight: var(--weight-semibold);
    color: var(--color-text-primary);
    line-height: var(--leading-tight);
  }

  .variant-transparent .logo-name {
    color: var(--color-white);
  }

  .logo-tagline {
    font-family: var(--font-body);
    font-size: var(--text-xs);
    color: var(--color-text-muted);
    letter-spacing: var(--tracking-wide);
  }

  .variant-transparent .logo-tagline {
    color: rgba(255, 255, 255, 0.7);
  }

  /* Desktop nav */
  .desktop-nav {
    display: none;
    align-items: center;
    gap: var(--space-8);
  }

  @media (min-width: 768px) {
    .desktop-nav {
      display: flex;
    }
  }

  /* Header actions */
  .header-actions {
    display: none;
  }

  @media (min-width: 768px) {
    .header-actions {
      display: flex;
      align-items: center;
      gap: var(--space-4);
    }
  }

  /* Mobile menu toggle */
  .mobile-menu-toggle {
    display: flex;
    flex-direction: column;
    justify-content: center;
    gap: 5px;
    width: 2.5rem;
    height: 2.5rem;
    padding: var(--space-2);
    background: none;
    border: none;
    cursor: pointer;
  }

  @media (min-width: 768px) {
    .mobile-menu-toggle {
      display: none;
    }
  }

  .bar {
    display: block;
    width: 100%;
    height: 2px;
    background-color: var(--color-text-primary);
    transition:
      transform var(--transition-base),
      opacity var(--transition-base);
  }

  .variant-transparent .bar {
    background-color: var(--color-white);
  }

  .mobile-menu-toggle.open .bar:nth-child(1) {
    transform: translateY(7px) rotate(45deg);
  }

  .mobile-menu-toggle.open .bar:nth-child(2) {
    opacity: 0;
  }

  .mobile-menu-toggle.open .bar:nth-child(3) {
    transform: translateY(-7px) rotate(-45deg);
  }

  /* Mobile nav */
  .mobile-nav {
    display: flex;
    flex-direction: column;
    gap: var(--space-2);
    padding: var(--space-4) var(--container-padding) var(--space-6);
    background-color: var(--color-bg-primary);
    border-bottom: 1px solid var(--color-border);
  }

  @media (min-width: 768px) {
    .mobile-nav {
      display: none;
    }
  }

  .mobile-nav-link {
    display: block;
    padding: var(--space-3) var(--space-4);
    font-family: var(--font-body);
    font-size: var(--text-base);
    font-weight: var(--weight-medium);
    color: var(--color-text-primary);
    text-decoration: none;
    border-radius: var(--radius-md);
    transition: background-color var(--transition-fast);
  }

  .mobile-nav-link:hover {
    background-color: var(--color-bg-secondary);
  }
</style>
