<script>
  import "../app.css";
  import Appbar from "../components/appbar.svelte";
</script>

<Appbar />

<main class="overflow-x-hidden">
  <div class="container mx-auto max-w-5xl px-5 py-10">
    <slot />
  </div>
</main>
