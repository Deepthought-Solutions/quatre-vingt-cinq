<script lang="ts">
  import { Hero, EngagementsSection } from '$lib/components/organisms';
  import { Text, Button } from '$lib/components/atoms';

  const engagements = [
    'Un interlocuteur unique',
    'Une approche sur-mesure',
    'Une implication personnelle sur chaque mission',
    'Une confidentialité absolue',
    'Une relation de confiance dans le temps',
  ];

  const fonctionOptions = [
    'DG / CEO',
    'DRH',
    'DSI',
    'Directeur industriel',
    'Directeur financier',
    'Autre',
  ];

  const objetOptions = [
    'Nouveau recrutement',
    'Conseil RH / organisation',
    'Échange exploratoire',
    'Autre',
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
        entre le dirigeant et son recruteur. Chaque mission est pilotée personnellement, sans
        délégation, sans automatisation, sans standardisation. Nous assumons un recrutement
        exigeant, responsable et durable.
      </Text>
    </div>
  </div>
</section>

<section class="founder-section">
  <div class="container">
    <div class="founder-content">
      <div class="founder-photo-wrapper">
        <div class="founder-photo-placeholder">
          <span class="founder-initials">SA</span>
        </div>
        <p class="founder-caption">Samuel Assoun — Fondateur & Consultant</p>
      </div>
      <div class="founder-info">
        <a
          href="https://www.linkedin.com/company/85-conseil-et-recrutement/?viewAsMember=true"
          class="linkedin-link"
          target="_blank"
          rel="noopener noreferrer"
          aria-label="LinkedIn 85 Conseil et Recrutement"
        >
          <svg viewBox="0 0 24 24" fill="currentColor" width="24" height="24">
            <path
              d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433c-1.144 0-2.063-.926-2.063-2.065 0-1.138.92-2.063 2.063-2.063 1.14 0 2.064.925 2.064 2.063 0 1.139-.925 2.065-2.064 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z"
            />
          </svg>
          <span>Suivez-nous sur LinkedIn</span>
        </a>
      </div>
    </div>
  </div>
</section>

<EngagementsSection overline="Nos engagements" title="Ce qui nous définit" {engagements} />

<section class="philosophy-section">
  <div class="container">
    <blockquote class="main-quote">
      <p class="main-quote-text">
        &laquo;&nbsp;Le recrutement n'est pas un acte administratif. C'est une décision structurante
        pour l'entreprise. Nous l'exerçons comme un métier d'art.&nbsp;&raquo;
      </p>
    </blockquote>
  </div>
</section>

<section class="contact-form-section" id="contact">
  <div class="container">
    <div class="form-header">
      <h2 class="form-title">Échanger avec un consultant</h2>
      <p class="form-intro">
        Vous souhaitez évoquer un projet de recrutement, un enjeu stratégique ou simplement échanger
        sur vos besoins ? Nous vous répondrons dans les meilleurs délais avec la discrétion et
        l'exigence qui caractérisent notre approche.
      </p>
    </div>

    <form
      class="contact-form"
      action="mailto:contact@quatre-vingt-cinq.fr"
      method="POST"
      enctype="text/plain"
    >
      <div class="form-grid">
        <div class="form-field">
          <label for="name" class="form-label">Nom et prénom</label>
          <input type="text" id="name" name="name" class="form-input" required />
        </div>

        <div class="form-field">
          <label for="company" class="form-label">Entreprise</label>
          <input type="text" id="company" name="company" class="form-input" required />
        </div>

        <div class="form-field">
          <label for="fonction" class="form-label">Fonction</label>
          <select id="fonction" name="fonction" class="form-input form-select" required>
            <option value="" disabled selected>Sélectionnez votre fonction</option>
            {#each fonctionOptions as option}
              <option value={option}>{option}</option>
            {/each}
          </select>
        </div>

        <div class="form-field">
          <label for="email" class="form-label">Email professionnel</label>
          <input type="email" id="email" name="email" class="form-input" required />
        </div>

        <div class="form-field">
          <label for="phone" class="form-label">
            Téléphone <span class="form-optional">(facultatif)</span>
          </label>
          <input type="tel" id="phone" name="phone" class="form-input" />
          <span class="form-hint">Pour faciliter l'échange si besoin.</span>
        </div>

        <div class="form-field">
          <label for="objet" class="form-label">Objet de votre demande</label>
          <select id="objet" name="objet" class="form-input form-select" required>
            <option value="" disabled selected>Sélectionnez un objet</option>
            {#each objetOptions as option}
              <option value={option}>{option}</option>
            {/each}
          </select>
        </div>

        <div class="form-field form-field-full">
          <label for="message" class="form-label">Votre message</label>
          <textarea
            id="message"
            name="message"
            class="form-input form-textarea"
            rows="5"
            placeholder="Décrivez brièvement votre contexte ou votre besoin."
          ></textarea>
        </div>
      </div>

      <p class="form-confidentiality">
        Vos informations sont traitées de manière strictement confidentielle et ne seront jamais
        transmises à des tiers.
      </p>

      <div class="form-submit">
        <Button variant="primary" size="lg" type="submit">Demander un échange</Button>
      </div>
    </form>
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
    max-width: 700px;
  }

  /* Founder */
  .founder-section {
    padding-block: var(--space-12) var(--section-padding-y);
    background-color: var(--color-bg-primary);
  }

  .founder-content {
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: var(--space-8);
  }

  @media (min-width: 768px) {
    .founder-content {
      flex-direction: row;
      align-items: flex-start;
    }
  }

  .founder-photo-wrapper {
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: var(--space-4);
    flex-shrink: 0;
  }

  .founder-photo-placeholder {
    width: 180px;
    height: 220px;
    background: linear-gradient(
      135deg,
      var(--color-gray-800) 0%,
      var(--color-primary) 50%,
      var(--color-accent-dark) 100%
    );
    border-radius: var(--radius-xl);
    display: flex;
    align-items: center;
    justify-content: center;
    box-shadow: var(--shadow-lg);
  }

  .founder-initials {
    font-family: var(--font-display);
    font-size: var(--text-4xl);
    font-weight: var(--weight-bold);
    color: var(--color-accent);
    opacity: 0.6;
  }

  .founder-caption {
    font-family: var(--font-body);
    font-size: var(--text-sm);
    color: var(--color-text-secondary);
    text-align: center;
    margin: 0;
    font-weight: var(--weight-medium);
  }

  .founder-info {
    display: flex;
    flex-direction: column;
    gap: var(--space-4);
  }

  .linkedin-link {
    display: inline-flex;
    align-items: center;
    gap: var(--space-2);
    color: var(--color-text-secondary);
    text-decoration: none;
    font-family: var(--font-body);
    font-size: var(--text-sm);
    font-weight: var(--weight-medium);
    transition: color var(--transition-fast);
  }

  .linkedin-link:hover {
    color: var(--color-accent);
  }

  /* Quote */
  .philosophy-section {
    padding-block: var(--section-padding-y);
    background-color: var(--color-bg-secondary);
  }

  .main-quote {
    margin: 0;
    text-align: center;
    max-width: 750px;
    margin-inline: auto;
  }

  .main-quote-text {
    font-family: var(--font-display);
    font-size: var(--text-2xl);
    font-weight: var(--weight-medium);
    color: var(--color-text-primary);
    line-height: var(--leading-relaxed);
    margin: 0;
  }

  /* Contact form */
  .contact-form-section {
    padding-block: var(--section-padding-y);
    background-color: var(--color-bg-primary);
  }

  .form-header {
    text-align: center;
    margin-bottom: var(--space-12);
  }

  .form-title {
    font-family: var(--font-display);
    font-size: var(--text-4xl);
    font-weight: var(--weight-semibold);
    color: var(--color-text-primary);
    margin: 0 0 var(--space-4) 0;
  }

  .form-intro {
    font-family: var(--font-body);
    font-size: var(--text-lg);
    color: var(--color-text-secondary);
    line-height: var(--leading-relaxed);
    max-width: 650px;
    margin: 0 auto;
  }

  .contact-form {
    max-width: 700px;
    margin-inline: auto;
  }

  .form-grid {
    display: grid;
    grid-template-columns: 1fr;
    gap: var(--space-6);
  }

  @media (min-width: 640px) {
    .form-grid {
      grid-template-columns: 1fr 1fr;
    }
  }

  .form-field {
    display: flex;
    flex-direction: column;
    gap: var(--space-2);
  }

  .form-field-full {
    grid-column: 1 / -1;
  }

  .form-label {
    font-family: var(--font-body);
    font-size: var(--text-sm);
    font-weight: var(--weight-medium);
    color: var(--color-text-primary);
  }

  .form-optional {
    font-weight: var(--weight-normal);
    color: var(--color-text-muted);
  }

  .form-input {
    font-family: var(--font-body);
    font-size: var(--text-base);
    color: var(--color-text-primary);
    background-color: var(--color-bg-secondary);
    border: 1px solid var(--color-border);
    border-radius: var(--radius-md);
    padding: var(--space-3) var(--space-4);
    transition:
      border-color var(--transition-fast),
      box-shadow var(--transition-fast);
    width: 100%;
    box-sizing: border-box;
  }

  .form-input:focus {
    outline: none;
    border-color: var(--color-accent);
    box-shadow: 0 0 0 3px var(--color-accent-muted);
  }

  .form-select {
    appearance: none;
    background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='12' height='12' viewBox='0 0 12 12'%3E%3Cpath fill='%236c757d' d='M6 8L1 3h10z'/%3E%3C/svg%3E");
    background-repeat: no-repeat;
    background-position: right var(--space-3) center;
    padding-right: var(--space-10);
    cursor: pointer;
  }

  .form-textarea {
    resize: vertical;
    min-height: 120px;
  }

  .form-hint {
    font-family: var(--font-body);
    font-size: var(--text-xs);
    color: var(--color-text-muted);
  }

  .form-confidentiality {
    font-family: var(--font-body);
    font-size: var(--text-xs);
    color: var(--color-text-muted);
    text-align: center;
    margin: var(--space-6) 0;
    font-style: italic;
  }

  .form-submit {
    display: flex;
    justify-content: center;
    margin-top: var(--space-4);
  }
</style>
