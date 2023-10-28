<script>
  import { statusList } from "$lib/objects.js";
  let currentStatus = statusList.find((x) => x.id === 20);
</script>

<section>
  <h1 class="text-3xl font-serif font-bold text-secondary pb-10">My order</h1>

  <ul class="steps steps-vertical w-full md:steps-horizontal">
    {#each statusList as status}
      {#if currentStatus}
        <li class="step {currentStatus.id >= status.id ? 'step-primary' : ''} ">
          {status.name}
        </li>
      {:else}
        <li class="step">{status.name}</li>
      {/if}
    {/each}
  </ul>

  {#if currentStatus}
    <div class="background-primary mt-10 p-10 rounded-tr-[50px]">
      <p class="text-2xl font-serif font-bold pb-2">{currentStatus.name}</p>
      <p class="text-lg">{currentStatus.description}</p>
    </div>
  {/if}
</section>

<style>
  .step {
    font-size: 14px;
  }

  .step::before {
    height: 0.1rem;
  }

  .step::after {
    height: 2.5rem;
    width: 2.5rem;
    background-color: #fff;
    border: 2px solid hsl(var(--b3) / var(--tw-bg-opacity));
    font-weight: 800;
  }

  .step-primary::after {
    background-color: hsl(var(--p));
    border: 2px solid hsl(var(--p));
  }

  .current::after {
    border: 2px solid hsl(var(--p) / var(--tw-bg-opacity));
    color: hsl(var(--bc) / var(--tw-text-opacity));
    background-color: #fff;
  }

  .background-primary {
    background-color: hsl(var(--p) / 0.1);
  }
</style>
