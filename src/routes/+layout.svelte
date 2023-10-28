<script>
  import "../app.css";
  import Appbar from "../components/appbar.svelte";
  import Login from "../components/login.svelte";
</script>

<Appbar />
<Login />
<main class="overflow-x-hidden">
  <div class="container mx-auto max-w-5xl px-5 py-10">
    <slot />
  </div>
</main>
