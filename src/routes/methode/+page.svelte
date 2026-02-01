<script lang="ts">
  import { Hero, MethodSection } from '$lib/components/organisms';
  import { SectionHeader, Card } from '$lib/components/molecules';
  import { Text } from '$lib/components/atoms';

  const methodSteps = [
    {
      title: 'Immersion métier',
      description: 'Comprendre votre réalité avant de chercher un profil.',
    },
    {
      title: 'Cartographie ciblée',
      description: 'Identifier les bons environnements, pas seulement les bons CV.',
    },
    {
      title: 'Approche directe individuelle',
      description: 'Contact humain, discours métier, confidentialité totale.',
    },
    {
      title: 'Évaluation approfondie',
      description: 'Parcours, posture, réalisations, compatibilité managériale.',
    },
    {
      title: "Suivi d'intégration",
      description: 'Accompagner la prise de poste dans la durée.',
    },
  ];

  const principles = [
    {
      title: "Pas d'annonces",
      description: "Nous ne diffusons pas d'annonces.",
    },
    {
      title: 'Pas de CVthèque',
      description: "Nous n'exploitons aucune CVthèque.",
    },
    {
      title: 'Pas de volume',
      description: 'Nous ne traitons jamais le recrutement comme un volume.',
    },
  ];
</script>

<svelte:head>
  <title>Notre méthode | 85 Conseil & Recrutement</title>
  <meta
    name="description"
    content="Une chasse artisanale, directe et confidentielle. Découvrez notre approche unique du recrutement par approche directe."
  />
</svelte:head>

<Hero
  overline="Notre méthode"
  title="Une chasse artisanale,"
  titleHighlight="directe et confidentielle."
  variant="default"
/>

<section class="principles-section">
  <div class="container">
    <div class="principles-grid">
      {#each principles as principle}
        <Card variant="outlined" padding="md">
          <div class="principle-item">
            <h3 class="principle-title">{principle.title}</h3>
            <Text variant="body" color="secondary">{principle.description}</Text>
          </div>
        </Card>
      {/each}
    </div>
  </div>
</section>

<section class="intro-section">
  <div class="container">
    <SectionHeader title="Notre travail consiste à :" align="left" />
    <ul class="work-list">
      <li>comprendre précisément un besoin,</li>
      <li>cartographier un marché,</li>
      <li>approcher individuellement les profils pertinents,</li>
      <li>évaluer leur capacité à s'inscrire durablement dans votre organisation.</li>
    </ul>
  </div>
</section>

<MethodSection
  overline="Les étapes"
  title="Notre méthode"
  steps={methodSteps}
  quote="L'artisan ne va pas vite. Il va juste."
/>

<style>
  .principles-section {
    padding-block: var(--section-padding-y);
    background-color: var(--color-bg-primary);
  }

  .container {
    max-width: var(--container-xl);
    margin-inline: auto;
    padding-inline: var(--container-padding);
  }

  .principles-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
    gap: var(--space-6);
  }

  .principle-item {
    display: flex;
    flex-direction: column;
    gap: var(--space-2);
    text-align: center;
  }

  .principle-title {
    font-family: var(--font-display);
    font-size: var(--text-xl);
    font-weight: var(--weight-semibold);
    color: var(--color-accent);
    margin: 0;
  }

  .intro-section {
    padding-block: var(--section-padding-y);
    background-color: var(--color-bg-primary);
  }

  .intro-section .container {
    max-width: var(--container-lg);
  }

  .work-list {
    margin-top: var(--space-8);
    padding-left: var(--space-6);
    list-style: none;
  }

  .work-list li {
    position: relative;
    padding-left: var(--space-4);
    margin-bottom: var(--space-3);
    font-family: var(--font-body);
    font-size: var(--text-lg);
    color: var(--color-text-secondary);
    line-height: var(--leading-relaxed);
  }

  .work-list li::before {
    content: '—';
    position: absolute;
    left: 0;
    color: var(--color-accent);
  }
</style>
