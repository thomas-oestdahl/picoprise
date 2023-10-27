<script>
  import Textfield from "../../components/textfield.svelte";
</script>

<section>
  <h1 class="text-3xl font-serif font-bold text-secondary">Order</h1>
  <form class="flex flex-col gap-4 py-2">
    <Textfield label="Fullname" placeholder="John Doe" type="text" />
    <Textfield label="Email" placeholder="john@doe.com " type="email" />
    <Textfield label="Address" placeholder="1234 Main St" type="text" />
    <Textfield label="Sauna volume" placeholder="1000" type="number" />

    <button
      class="btn btn-primary w-fit mt-5"
      type="submit"
      on:click|preventDefault={() => {
        alert("Order submitted!");
      }}
    >
      Submit
    </button>
  </form>
</section>

<style>
  /* Add any custom styles here */
</style>
