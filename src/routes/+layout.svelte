<script>
  import "../app.css";
  import Hero from "../components/hero.svelte";
</script>

<Hero />
<main>
  <div class="container mx-auto">
    <slot />
  </div>
</main>
