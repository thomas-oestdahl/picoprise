<script>
  import "../app.css";
  import Hero from "../components/hero.svelte";
  import Login from "../components/login.svelte";
</script>

<Hero />
<main>
  <Login />
  <div class="container mx-auto">
    <slot />
  </div>
</main>
