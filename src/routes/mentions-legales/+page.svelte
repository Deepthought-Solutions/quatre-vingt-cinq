<script lang="ts">
  import { Heading, Text } from '$lib/components/atoms';
</script>

<svelte:head>
  <title>Mentions légales | 85 Conseil & Recrutement</title>
  <meta
    name="description"
    content="Mentions légales du site 85 Conseil & Recrutement, cabinet de chasse de têtes."
  />
</svelte:head>

<section class="legal-page">
  <div class="container">
    <Heading level={1}>Mentions légales</Heading>

    <div class="content">
      <article class="legal-section">
        <Heading level={2}>Éditeur du site</Heading>
        <Text variant="body">
          85 Conseil & Recrutement<br />
          Cabinet de recrutement par approche directe<br />
          Chartres, France
        </Text>
      </article>

      <article class="legal-section">
        <Heading level={2}>Hébergement</Heading>
        <Text variant="body">
          Ce site est hébergé par GitHub Pages.<br />
          GitHub, Inc.<br />
          88 Colin P Kelly Jr St<br />
          San Francisco, CA 94107<br />
          United States
        </Text>
      </article>

      <article class="legal-section">
        <Heading level={2}>Propriété intellectuelle</Heading>
        <Text variant="body">
          L'ensemble du contenu de ce site (textes, images, graphismes, logo, icônes, etc.) est la
          propriété exclusive de 85 Conseil & Recrutement. Toute reproduction, distribution,
          modification, adaptation, retransmission ou publication de ces éléments est strictement
          interdite sans l'accord écrit préalable de 85 Conseil & Recrutement.
        </Text>
      </article>

      <article class="legal-section">
        <Heading level={2}>Protection des données personnelles</Heading>
        <Text variant="body">
          Conformément au Règlement Général sur la Protection des Données (RGPD), vous disposez d'un
          droit d'accès, de rectification, de suppression et d'opposition aux données personnelles
          vous concernant.
        </Text>
      </article>

      <article class="legal-section">
        <Heading level={2}>Cookies</Heading>
        <Text variant="body">
          Ce site n'utilise pas de cookies de tracking ou de publicité. Seuls les cookies
          strictement nécessaires au fonctionnement du site peuvent être utilisés.
        </Text>
      </article>
    </div>
  </div>
</section>

<style>
  .legal-page {
    padding-block: var(--section-padding-y);
    background-color: var(--color-bg-primary);
  }

  .container {
    max-width: var(--container-lg);
    margin-inline: auto;
    padding-inline: var(--container-padding);
  }

  .content {
    margin-top: var(--space-12);
    display: flex;
    flex-direction: column;
    gap: var(--space-10);
  }

  .legal-section {
    display: flex;
    flex-direction: column;
    gap: var(--space-4);
  }
</style>
