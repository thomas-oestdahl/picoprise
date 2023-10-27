<script>
  import { page } from "$app/stores";
  $: currentRoute = $page.url.pathname;
</script>

<section class="navbar bg-base-200 rounded-br-full">
  <div class="container mx-auto pr-10 flex items-center justify-between">
    <div class="flex flex-col items-start">
      <a class="text-2xl font-bold font-serif" href="/">
        <span class="text-primary">Pico</span>Prise<span
          class="text-primary ml-2"><i class="ph ph-wave-sine mr-2" /></span
        >
      </a>
      <p class="text-sm">Leading in sauna innovation</p>
    </div>
    <div class="flex flex-col items-start">
      <p class="text-lg">
        <i class="ph ph-user mr-3" />John Doe
      </p>
      <p class="text-sm">customer</p>
    </div>
  </div>
</section>
<nav class="navbar tabs mb-5">
  <div class="container mx-auto">
    <a
      class="tab tab-bordered {currentRoute === '/' ? 'tab-active' : ''}"
      href="/">Home</a
    >
    <a
      class="tab tab-bordered {currentRoute === '/order' ? 'tab-active' : ''}"
      href="/order">Order</a
    >
    <a
      class="tab tab-bordered {currentRoute === '/myorder' ? 'tab-active' : ''}"
      href="/myorder">My order</a
    >
  </div>
</nav>
