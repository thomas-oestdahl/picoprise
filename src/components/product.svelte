<div
  class="flex flex-col justify-between sm:flex-row bg-base-200 full-width mb-5"
>
  <div class="flex-grow md:text-right px-5 md:px-20 py-8">
    <h2 class="text-5xl md:text-7xl font-bold pb-2">
      <span class="text-primary">Pico</span>Pump
    </h2>
    <p class="py-5 text-lg md:text-2xl max-w-2xl ml-auto">
      As the undisputed champs of all things sauna, we proudly present to you
      the PicoPump – the sauna sensation that’s got the steamy world buzzing!
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
    class="min-w-[320px] min-h-[320px] md:min-w-[600px] md:min-h-[600px] flex"
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
