<script>
  import { page } from "$app/stores";
  $: currentRoute = $page.url.pathname;
</script>

<section class="navbar bg-slate-100 rounded-br-full">
  <div class="container mx-auto pr-10 flex items-center justify-between">
    <div class="flex flex-col items-start">
      <a class="text-2xl font-bold font-serif" href="/">
        <span class="text-primary">Pico</span>Prise<span
          class="text-primary ml-2"><i class="ph ph-wave-sine mr-2" /></span
        >
      </a>
      <p class="hidden sm:block text-sm">Leading the sauna innovation</p>
    </div>

    <nav>
      <ul class="menu menu-horizontal menu-sm rounded-box">
        <li>
          <details open>
            <summary
              ><i class="ph ph-user mr-1 text-lg" /><span class="pr-2"
                >John Doe</span
              ></summary
            >
            <ul class="w-32 z-10">
              <li class="pb-1"><a href="/">Home</a></li>
              <li class="pb-1"><a href="/order">Order</a></li>
              <li class="pb-1"><a href="/myorder">My order</a></li>
            </ul>
          </details>
        </li>
      </ul>
    </nav>
  </div>
</section>
