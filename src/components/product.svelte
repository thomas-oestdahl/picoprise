<div
  class="flex flex-col justify-center md:flex-row bg-slate-100 full-width mb-5"
>
  <div class="md:text-right px-5 md:px-10 xl:px-20 py-8">
    <h2 class="text-5xl md:text-7xl font-bold pb-5">
      <span class="text-primary">Pico</span>Pump
    </h2>
    <p class="pb-5 text-lg md:text-xl max-w-xl md:ml-auto">
      As the undisputed champs of all things sauna, we proudly present to you
      the PicoPump – the sauna sensation that’s got the steamy world buzzing!
    </p>
    <p class="pb-5 text-lg md:text-xl max-w-xl md:ml-auto">
      It’s not just a gizmo; it’s like having a personal sauna butler who knows
      all your sauna secrets. We’re not saying it’s magical, but it’s been known
      to turn a simple sweat session into a full-blown sauna fiesta!
    </p>
    <button
      class="btn btn-primary btn-lg"
      on:click={() => (window.location.pathname = "/order")}
      >Order now
    </button>
  </div>
  <div
    class="min-w-[320px] min-h-[320px] sm:min-w-[480px] sm:min-h-[480px] xl:min-w-[720px] flex"
  >
    <div
      class="bg-cover bg-no-repeat bg-center w-full rounded-tl-[20%]"
      style="background-image: url('/src/images/picopump.jpg ')"
    />
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
