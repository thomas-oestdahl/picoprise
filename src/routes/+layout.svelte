<script>
  import "../app.css";
  import Appbar from "../components/appbar.svelte";
</script>

<Appbar />

<main class="overflow-x-hidden">
  <div class="container mx-auto px-5">
    <slot />
  </div>
</main>
