<script>
  // @ts-nocheck

  import { page } from "$app/stores";
  import { account } from "../store/userInfo.js";
  import Login from "./login.svelte";
  $: currentRoute = $page.url.pathname;
</script>

<section class="navbar bg-base-200 rounded-br-full">
  <div
    class="container mx-auto px-3 sm:px-10 flex items-center justify-between"
  >
    <div class="flex flex-col items-start">
      <a class="text-2xl font-bold font-serif" href="/">
        <span class="text-primary">Pico</span>Prise<span
          class="text-primary ml-2"><i class="ph ph-wave-sine mr-2" /></span
        >
      </a>
      <p class="hidden sm:block text-sm">Leading the sauna innovation</p>
    </div>
    {#if $account}
      <nav>
        <ul class="menu menu-horizontal menu-sm rounded-box">
          <li>
            <details open>
              <summary>
                <i class="ph ph-user mr-1 text-lg" /><span class="pr-2"
                  >{$account?.name}</span
                >
              </summary>
              <ul class="w-32 z-10">
                <li class="pb-1"><a href="/">Home</a></li>
                <li class="pb-1"><a href="/order">Order</a></li>
                <li class="pb-1"><a href="/myorder">My order</a></li>
                <li class="pb-1"><a href="/dashboard">Dashboard</a></li>
              </ul>
            </details>
          </li>
        </ul>
      </nav>
    {:else}
      <Login />
    {/if}
  </div>
</section>
