<script>
  import '../app.css';
  let { children } = $props();
</script>

<svelte:head>
  <title>quatre-vingt-cinq</title>
</svelte:head>

{@render children()}
