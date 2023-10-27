<div class="flex bg-base-200 full-width mb-5">
  <div class="w-3/5 text-right px-20 py-8">
    <h2 class="text-7xl font-bold pb-2">
      <span class="text-primary">Pico</span>Pump
    </h2>
    <p class="py-8 text-2xl max-w-2xl ml-auto">
      As a global leader in sauna technology, we are the proud manufacturers
      of PicoPump - the revolutionary automatic humidity regulator that has
      transformed sauna experiences for thousands worldwide. PicoPump isn't
      just a product; it's a promise of precision, tailored to each sauna's
      unique needs.
    </p>
    <button
        class="btn btn-secondary btn-lg"
        on:click={() => (window.location.pathname = "/order")}>Order now
    </button>
  </div>
  <div class="w-2/5 flex">
    <div class="bg-cover bg-no-repeat bg-center w-full rounded-tl-[20%]" style="background-image: url('/src/images/picopump.jpg ')"></div>
  </div>
</div>

<style>
  .full-width {
    width: 100vw;
    position: relative;
    left: 50%;
    right: 50%;
    margin-left: -50vw;
    margin-right: -50vw;
  }
</style>