<script>
  import { navigate } from "svelte-routing";
</script>

<div class="flex bg-base-200 w-full py-8 full-width">
  <div class="w-3/5 text-right px-20">
    <h2 class="text-7xl font-bold pb-2">
      <span class="text-primary">Pico</span>Pump
    </h2>
    <p class="py-8 text-base">
      As a global leader in sauna technology, we are the proud manufacturers
      of PicoPump - the revolutionary automatic humidity regulator that has
      transformed sauna experiences for thousands worldwide. PicoPump isn't
      just a product; it's a promise of precision, tailored to each sauna's
      unique needs.
    </p>
    <div class="max-w-xl ml-auto pb-10">
      <p class="text-2xl pb-2">
        Why PicoPump?
      </p>
      <ul class="text-left list-disc">
        <li class="py-1">
          <span class="font-bold">Precision Control:</span> PicoPump gives you precise control over the temperature and humidity in your sauna.
          Say goodbye to fluctuating conditions and hello to a sauna that’s always just the way you like it.
        </li>
        <li class="py-1">
          <span class="font-bold">Easy Installation:</span> Installing PicoPump is a breeze. It comes with a user-friendly manual, and our
          customer support team is always ready to assist you. You’ll have your sauna climate under control in no time.
        </li>
        <li class="py-1">
          <span class="font-bold">Global Reach:</span> PicoPump is going global, and it’s available in every corner of the world. No matter where
          you’re located, we’re committed to bringing the benefits of this exceptional sauna accessory to your doorstep.
        </li>
        <li class="py-1">
          <span class="font-bold">Built to Last:</span> Crafted in the challenging climate of Norway, PicoPump is designed to endure. Its robust build
          and durable components ensure that it can withstand the harshest conditions, providing you with reliable, long-lasting performance.
        </li>
      </ul>
    </div>
    <button
      class="btn btn-secondary btn-lg"
      on:click={() => navigate("/order", { replace: true })}>Order now</button
    >
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