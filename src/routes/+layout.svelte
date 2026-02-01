<script lang="ts">
  import '../app.css';
  import { Header, Footer } from '$lib/components/organisms';

  let { children } = $props();
</script>

<svelte:head>
  <title>85 Conseil & Recrutement | Chasse de têtes</title>
  <meta
    name="description"
    content="Cabinet indépendant de chasse de têtes, spécialisé dans les recrutements à fort impact humain et opérationnel. IT, Industrie, Finance, RH, Fonctions clés."
  />
  <link rel="preconnect" href="https://fonts.googleapis.com" />
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin="anonymous" />
</svelte:head>

<div class="app">
  <Header />
  <main class="main">
    {@render children()}
  </main>
  <Footer />
</div>

<style>
  .app {
    display: flex;
    flex-direction: column;
    min-height: 100vh;
  }

  .main {
    flex: 1;
  }
</style>
