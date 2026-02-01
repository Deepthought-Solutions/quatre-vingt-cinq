<script lang="ts">
  import { Hero, ExpertiseSection, ValueProposition } from '$lib/components/organisms';
  import { QuoteBlock } from '$lib/components/molecules';

  const expertises = [
    {
      title: 'IT & Digital',
      items: ['DSI', 'CTO', 'Data', 'Engineering', 'Cybersécurité'],
    },
    {
      title: 'Industrie',
      items: ["Direction d'usine", 'Ingénierie', 'Méthodes', 'Maintenance'],
    },
    {
      title: 'Finance',
      items: ['Direction financière', 'Contrôle de gestion'],
    },
    {
      title: 'Ressources Humaines',
      items: ['DRH', 'RRH', 'Développement RH'],
    },
    {
      title: 'Fonctions clés',
      items: ['Cadres dirigeants', 'Experts', 'Directions opérationnelles'],
    },
  ];

  const valueItems = [
    {
      title: 'Postes clés',
      description: 'Nous intervenons lorsque le recrutement ne peut être standardisé.',
    },
    {
      title: 'Environnements exigeants',
      description: 'Des contextes où chaque décision de recrutement est structurante.',
    },
    {
      title: 'Travail sur mesure',
      description: "Chaque mission est traitée avec la précision d'un travail artisanal.",
    },
  ];
</script>

<svelte:head>
  <title>85 Conseil & Recrutement | Expertise</title>
</svelte:head>

<Hero
  overline="Artisan du recrutement"
  title="Recruter est un métier."
  titleHighlight="Le nôtre est un artisanat."
  subtitle="Cabinet indépendant de chasse de têtes, spécialisé dans les recrutements à fort impact humain et opérationnel."
  variant="default"
  showLogo
  ctaLabel="Découvrir notre méthode"
  ctaHref="/methode"
/>

<ValueProposition items={valueItems} />

<ExpertiseSection title="Domaines d'intervention" {expertises} />

<section class="quote-section">
  <div class="container">
    <QuoteBlock
      quote="Nous intervenons lorsque le recrutement ne peut être standardisé : postes clés, environnements exigeants, décisions engageantes."
      variant="centered"
    />
  </div>
</section>

<section id="contact" class="contact-section">
  <div class="container">
    <div class="contact-content">
      <h2 class="contact-title">Parlons de votre projet</h2>
      <p class="contact-text">
        Vous avez un recrutement stratégique à réaliser ? Contactez-nous pour échanger sur votre
        besoin.
      </p>
      <a href="mailto:contact@85conseil.fr" class="contact-link">contact@85conseil.fr</a>
    </div>
  </div>
</section>

<style>
  .quote-section {
    padding-block: var(--section-padding-y);
    background-color: var(--color-bg-secondary);
  }

  .container {
    max-width: var(--container-lg);
    margin-inline: auto;
    padding-inline: var(--container-padding);
  }

  .contact-section {
    padding-block: var(--section-padding-y);
    background-color: var(--color-primary);
    color: var(--color-text-inverse);
  }

  .contact-content {
    display: flex;
    flex-direction: column;
    align-items: center;
    text-align: center;
    gap: var(--space-6);
  }

  .contact-title {
    font-family: var(--font-display);
    font-size: var(--text-4xl);
    font-weight: var(--weight-semibold);
    margin: 0;
  }

  .contact-text {
    font-size: var(--text-lg);
    opacity: 0.85;
    max-width: 500px;
    margin: 0;
  }

  .contact-link {
    display: inline-flex;
    align-items: center;
    gap: var(--space-2);
    font-size: var(--text-xl);
    font-weight: var(--weight-medium);
    color: var(--color-accent);
    text-decoration: none;
    transition: opacity var(--transition-fast);
  }

  .contact-link:hover {
    opacity: 0.8;
  }
</style>
