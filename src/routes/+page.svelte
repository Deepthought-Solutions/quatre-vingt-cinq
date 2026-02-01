<script lang="ts">
  import { base } from '$app/paths';
</script>

<main>
  <section class="hero">
    <div class="logo">
      <span class="number">85</span>
    </div>
    <h1>quatre-vingt-cinq</h1>
    <p class="tagline">L'excellence au service de l'innovation</p>
  </section>

  <section class="content">
    <div class="card">
      <h2>Notre Vision</h2>
      <p>
        Quatre-vingt-cinq incarne la perfection dans chaque détail.
        Nous créons des expériences numériques qui marquent les esprits.
      </p>
    </div>

    <div class="card">
      <h2>Notre Approche</h2>
      <p>
        Alliant créativité et expertise technique, nous transformons
        vos idées en réalités digitales exceptionnelles.
      </p>
    </div>

    <div class="card">
      <h2>Notre Engagement</h2>
      <p>
        Chaque projet est une nouvelle opportunité de repousser
        les limites et d'atteindre l'excellence.
      </p>
    </div>
  </section>

  <footer>
    <p>&copy; {new Date().getFullYear()} quatre-vingt-cinq. Tous droits réservés.</p>
  </footer>
</main>

<style>
  main {
    min-height: 100vh;
    display: flex;
    flex-direction: column;
  }

  .hero {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    min-height: 70vh;
    text-align: center;
    padding: 2rem;
    background: linear-gradient(135deg, var(--color-primary) 0%, var(--color-secondary) 100%);
    position: relative;
    overflow: hidden;
  }

  .hero::before {
    content: '';
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    background: radial-gradient(circle at 30% 50%, rgba(233, 69, 96, 0.1) 0%, transparent 50%),
                radial-gradient(circle at 70% 80%, rgba(233, 69, 96, 0.08) 0%, transparent 40%);
    pointer-events: none;
  }

  .logo {
    position: relative;
    margin-bottom: 2rem;
  }

  .number {
    font-family: var(--font-display);
    font-size: clamp(6rem, 20vw, 12rem);
    font-weight: 700;
    color: transparent;
    -webkit-text-stroke: 2px var(--color-accent);
    text-stroke: 2px var(--color-accent);
    line-height: 1;
    animation: pulse 3s ease-in-out infinite;
  }

  @keyframes pulse {
    0%, 100% {
      opacity: 1;
      transform: scale(1);
    }
    50% {
      opacity: 0.8;
      transform: scale(1.02);
    }
  }

  h1 {
    font-size: clamp(2rem, 5vw, 3.5rem);
    margin-bottom: 1rem;
    letter-spacing: 0.1em;
    text-transform: lowercase;
  }

  .tagline {
    font-size: clamp(1rem, 2.5vw, 1.25rem);
    color: var(--color-text);
    opacity: 0.8;
    max-width: 600px;
  }

  .content {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
    gap: 2rem;
    padding: 4rem 2rem;
    max-width: 1200px;
    margin: 0 auto;
    width: 100%;
  }

  .card {
    background: var(--color-secondary);
    padding: 2rem;
    border-radius: 8px;
    border-left: 3px solid var(--color-accent);
    transition: transform 0.3s ease, box-shadow 0.3s ease;
  }

  .card:hover {
    transform: translateY(-4px);
    box-shadow: 0 10px 40px rgba(233, 69, 96, 0.15);
  }

  .card h2 {
    font-size: 1.5rem;
    margin-bottom: 1rem;
    color: var(--color-accent);
  }

  .card p {
    color: var(--color-text);
    opacity: 0.9;
  }

  footer {
    margin-top: auto;
    padding: 2rem;
    text-align: center;
    background: var(--color-secondary);
  }

  footer p {
    opacity: 0.7;
    font-size: 0.875rem;
  }
</style>
