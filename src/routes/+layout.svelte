<script>
  import "../app.css";
  import Appbar from "../components/appbar.svelte";
  import Login from "../components/login.svelte";
</script>

<Appbar />
<Login />
<main class="overflow-x-hidden">
  <div class="container mx-auto px-5">
    <slot />
  </div>
</main>
