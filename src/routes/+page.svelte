<script lang="ts">
  import { base } from '$app/paths';
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
      title: 'Droit & Juridique',
      items: ['Directeur Juridique', 'Juriste Senior', 'Compliance', 'RGPD'],
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
  ctaHref="{base}/methode"
>
  {#snippet children()}
    <div class="credibility-block">
      <div class="credibility-items">
        <span class="credibility-item">Approche directe exclusivement</span>
        <span class="credibility-sep">·</span>
        <span class="credibility-item">Un interlocuteur unique</span>
        <span class="credibility-sep">·</span>
        <span class="credibility-item">Recrutements stratégiques</span>
      </div>
      <p class="credibility-sectors">IT · Industrie · Finance · RH · Juridique</p>
    </div>
  {/snippet}
</Hero>

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
        Vous avez un recrutement stratégique à conduire ? Échangeons sur votre contexte et vos
        enjeux. Nous vous répondrons avec la discrétion et l'exigence qui caractérisent notre
        approche.
      </p>
      <a href="{base}/qui-sommes-nous#contact" class="contact-cta">Nous contacter</a>
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

  .contact-cta {
    display: inline-block;
    font-family: var(--font-body);
    font-size: var(--text-base);
    font-weight: var(--weight-semibold);
    color: var(--color-primary);
    background-color: var(--color-accent);
    padding: var(--space-3) var(--space-8);
    border-radius: var(--radius-md);
    text-decoration: none;
    transition:
      background-color var(--transition-fast),
      opacity var(--transition-fast);
  }

  .contact-cta:hover {
    opacity: 0.9;
  }

  /* Credibility block */
  .credibility-block {
    display: flex;
    flex-direction: column;
    gap: var(--space-4);
  }

  .credibility-items {
    display: flex;
    flex-wrap: wrap;
    align-items: center;
    gap: var(--space-2);
  }

  .credibility-item {
    font-family: var(--font-body);
    font-size: var(--text-sm);
    font-weight: var(--weight-medium);
    color: var(--color-white);
    letter-spacing: var(--tracking-wide);
  }

  .credibility-sep {
    color: var(--color-accent);
    font-size: var(--text-base);
  }

  .credibility-sectors {
    font-family: var(--font-body);
    font-size: var(--text-xs);
    color: rgba(255, 255, 255, 0.5);
    letter-spacing: var(--tracking-wider);
    margin: 0;
  }
</style>
