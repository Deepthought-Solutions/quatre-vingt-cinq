<script lang="ts">
  import { Hero, EngagementsSection } from '$lib/components/organisms';
  import { QuoteBlock } from '$lib/components/molecules';
  import { Text } from '$lib/components/atoms';

  const engagements = [
    'Un interlocuteur unique',
    'Une approche sur-mesure',
    'Une implication personnelle sur chaque mission',
    'Une confidentialité absolue',
    'Une relation de confiance dans le temps',
  ];
</script>

<svelte:head>
  <title>Qui sommes-nous | 85 Conseil & Recrutement</title>
  <meta
    name="description"
    content="Cabinet à taille humaine, fondé sur une relation directe entre le dirigeant et son recruteur. Indépendants par choix, engagés par conviction."
  />
</svelte:head>

<Hero
  overline="Qui sommes-nous"
  title="Indépendants par choix."
  titleHighlight="Engagés par conviction."
  variant="default"
/>

<section class="about-section">
  <div class="container">
    <div class="about-content">
      <Text variant="lead">
        85 Conseil & Recrutement est un cabinet à taille humaine, fondé sur une relation directe
        entre le dirigeant et son recruteur.
      </Text>
      <Text variant="body-lg" color="secondary">
        Chaque mission est pilotée personnellement, sans délégation, sans automatisation, sans
        standardisation.
      </Text>
      <Text variant="body-lg" color="secondary">
        Nous assumons un recrutement exigeant, responsable et durable.
      </Text>
    </div>
  </div>
</section>

<EngagementsSection overline="Nos engagements" title="Ce qui nous définit" {engagements} />

<section class="philosophy-section">
  <div class="container">
    <QuoteBlock
      quote="Le recrutement n'est pas un acte administratif. C'est une décision structurante pour l'entreprise."
      variant="centered"
    />
    <div class="closing-statement">
      <Text variant="lead" color="accent" align="center">
        Nous l'exerçons comme un métier d'art.
      </Text>
    </div>
  </div>
</section>

<style>
  .about-section {
    padding-block: var(--section-padding-y);
    background-color: var(--color-bg-primary);
  }

  .container {
    max-width: var(--container-lg);
    margin-inline: auto;
    padding-inline: var(--container-padding);
  }

  .about-content {
    display: flex;
    flex-direction: column;
    gap: var(--space-6);
    max-width: 700px;
  }

  .philosophy-section {
    padding-block: var(--section-padding-y);
    background-color: var(--color-bg-secondary);
  }

  .closing-statement {
    margin-top: var(--space-8);
  }
</style>
