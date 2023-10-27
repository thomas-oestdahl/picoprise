<script>
  import "../app.css";
  import Appbar from "../components/appbar.svelte";
  import Hero from "../components/hero.svelte";
</script>

<Appbar />

<Hero />
<main>
  <div class="container mx-auto">
    <slot />
  </div>
</main>
