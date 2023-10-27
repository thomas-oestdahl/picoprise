<script>
  import "../app.css";
  import Appbar from "../components/appbar.svelte";
</script>

<Appbar />

<main>
  <div class="container mx-auto">
    <slot />
  </div>
</main>
