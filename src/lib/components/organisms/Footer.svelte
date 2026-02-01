<script lang="ts">
  import { Logo, Text, Divider } from '../atoms';

  const currentYear = new Date().getFullYear();

  const expertises = ['IT & Digital', 'Industrie', 'Finance', 'RH', 'Fonctions clés'];

  const navigation = [
    { href: '/', label: 'Expertise' },
    { href: '/methode', label: 'Notre méthode' },
    { href: '/qui-sommes-nous', label: 'Qui sommes-nous' },
  ];
</script>

<footer class="footer">
  <div class="footer-container">
    <div class="footer-main">
      <div class="footer-brand">
        <a href="/" class="logo-link" aria-label="85 Conseil & Recrutement - Accueil">
          <Logo size="md" />
        </a>
        <div class="brand-info">
          <h3 class="brand-name">85 Conseil & Recrutement</h3>
          <Text variant="caption" color="muted">Artisan du recrutement par approche directe</Text>
        </div>
      </div>

      <div class="footer-columns">
        <div class="footer-column">
          <h4 class="column-title">Navigation</h4>
          <nav class="footer-nav" aria-label="Navigation secondaire">
            {#each navigation as item}
              <a href={item.href} class="footer-link">{item.label}</a>
            {/each}
          </nav>
        </div>

        <div class="footer-column">
          <h4 class="column-title">Domaines</h4>
          <ul class="expertise-list">
            {#each expertises as expertise}
              <li class="expertise-tag">{expertise}</li>
            {/each}
          </ul>
        </div>

        <div class="footer-column">
          <h4 class="column-title">Contact</h4>
          <address class="contact-info">
            <Text variant="body-sm" color="secondary" as="span">Chartres</Text>
            <Text variant="body-sm" color="secondary" as="span">Intervention nationale</Text>
          </address>
          <div class="social-links">
            <a
              href="https://linkedin.com"
              class="social-link"
              aria-label="LinkedIn"
              target="_blank"
              rel="noopener noreferrer"
            >
              <svg viewBox="0 0 24 24" fill="currentColor" width="20" height="20">
                <path
                  d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433c-1.144 0-2.063-.926-2.063-2.065 0-1.138.92-2.063 2.063-2.063 1.14 0 2.064.925 2.064 2.063 0 1.139-.925 2.065-2.064 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z"
                />
              </svg>
            </a>
          </div>
        </div>
      </div>
    </div>

    <Divider variant="solid" spacing="md" />

    <div class="footer-bottom">
      <Text variant="caption" color="muted">
        © {currentYear} 85 Conseil & Recrutement. Tous droits réservés.
      </Text>
      <div class="legal-links">
        <a href="/mentions-legales" class="legal-link">Mentions légales</a>
      </div>
    </div>
  </div>
</footer>

<style>
  .footer {
    background-color: var(--color-bg-secondary);
    padding-block: var(--space-16) var(--space-8);
  }

  .footer-container {
    max-width: var(--container-xl);
    margin-inline: auto;
    padding-inline: var(--container-padding);
  }

  .footer-main {
    display: grid;
    gap: var(--space-12);
  }

  @media (min-width: 768px) {
    .footer-main {
      grid-template-columns: 1fr 2fr;
      gap: var(--space-16);
    }
  }

  /* Brand */
  .footer-brand {
    display: flex;
    flex-direction: column;
    gap: var(--space-4);
  }

  .logo-link {
    display: inline-block;
    text-decoration: none;
  }

  .brand-info {
    display: flex;
    flex-direction: column;
    gap: var(--space-1);
  }

  .brand-name {
    font-family: var(--font-display);
    font-size: var(--text-lg);
    font-weight: var(--weight-semibold);
    color: var(--color-text-primary);
    margin: 0;
  }

  /* Columns */
  .footer-columns {
    display: grid;
    gap: var(--space-8);
  }

  @media (min-width: 640px) {
    .footer-columns {
      grid-template-columns: repeat(3, 1fr);
    }
  }

  .footer-column {
    display: flex;
    flex-direction: column;
    gap: var(--space-4);
  }

  .column-title {
    font-family: var(--font-body);
    font-size: var(--text-sm);
    font-weight: var(--weight-semibold);
    color: var(--color-text-primary);
    text-transform: uppercase;
    letter-spacing: var(--tracking-wide);
    margin: 0;
  }

  /* Navigation */
  .footer-nav {
    display: flex;
    flex-direction: column;
    gap: var(--space-2);
  }

  .footer-link {
    font-family: var(--font-body);
    font-size: var(--text-sm);
    color: var(--color-text-secondary);
    text-decoration: none;
    transition: color var(--transition-fast);
  }

  .footer-link:hover {
    color: var(--color-accent);
  }

  /* Expertise list */
  .expertise-list {
    display: flex;
    flex-wrap: wrap;
    gap: var(--space-2);
    list-style: none;
    margin: 0;
    padding: 0;
  }

  .expertise-tag {
    font-family: var(--font-body);
    font-size: var(--text-xs);
    color: var(--color-text-secondary);
    background-color: var(--color-bg-primary);
    padding: var(--space-1) var(--space-2);
    border-radius: var(--radius-sm);
  }

  /* Contact */
  .contact-info {
    display: flex;
    flex-direction: column;
    gap: var(--space-1);
    font-style: normal;
  }

  .social-links {
    display: flex;
    gap: var(--space-3);
    margin-top: var(--space-2);
  }

  .social-link {
    display: flex;
    align-items: center;
    justify-content: center;
    width: 2.25rem;
    height: 2.25rem;
    color: var(--color-text-secondary);
    background-color: var(--color-bg-primary);
    border-radius: var(--radius-md);
    transition:
      color var(--transition-fast),
      background-color var(--transition-fast);
  }

  .social-link:hover {
    color: var(--color-white);
    background-color: var(--color-accent);
  }

  /* Bottom */
  .footer-bottom {
    display: flex;
    flex-direction: column;
    gap: var(--space-4);
    align-items: center;
    text-align: center;
  }

  @media (min-width: 640px) {
    .footer-bottom {
      flex-direction: row;
      justify-content: space-between;
      text-align: left;
    }
  }

  .legal-links {
    display: flex;
    gap: var(--space-4);
  }

  .legal-link {
    font-family: var(--font-body);
    font-size: var(--text-xs);
    color: var(--color-text-muted);
    text-decoration: none;
    transition: color var(--transition-fast);
  }

  .legal-link:hover {
    color: var(--color-accent);
  }
</style>
