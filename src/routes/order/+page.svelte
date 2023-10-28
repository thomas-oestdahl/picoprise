<script>
  import Textfield from "../../components/textfield.svelte";
    import { token } from "../../store/userInfo.js";
    import { account } from "../../store/userInfo.js";

  const fetchUrl = "https://picoprice.azurewebsites.net/api/Order";

  const showToast = () => {
    const toast = document.querySelector(".toast");
    toast?.classList.add("show");
    toast?.classList.remove("hidden");
    setTimeout(() => {
      toast?.classList.remove("show");
      toast?.classList.add("hidden");
    }, 3000);
  };

  // @ts-ignore
  const submitProduct = async (event) => {
    const formData = new FormData(event.target);
    const data = Object.fromEntries(formData.entries());
    console.log(data);

    const order = {
      customer: {
        name: data.fullname,
        email: data.email,
      },
      shippingAddress: data.address,
      product: {
        saunaVolum: data.volume,
      },
    };

    const res = await fetch(fetchUrl, {
      method: "POST",
      headers: {
        "Content-Type": "application/json",
        "Authorization": "Bearer " + $token,
      },
      body: JSON.stringify(order),
    });

    console.log(res);
    event.target.reset();
    showToast();
  };
</script>

<section class="">
  <h1 class="text-3xl font-serif font-bold text-secondary">Order</h1>
  <div class="flex flex-col-reverse sm:flex-row">
    <form
      id="order-form"
      on:submit|preventDefault={submitProduct}
      class="flex flex-col gap-4 py-2 flex-grow"
    >
      <Textfield
        label="Fullname"
        placeholder="John Doe"
        type="text"
        name="fullname"
        value={$account?.name}
      />
      <Textfield
        name="email"
        label="Email"
        placeholder="john@doe.com "
        type="email"
        value={$account?.username}
      />
      <Textfield
        name="address"
        label="Address"
        placeholder="1234 Main St"
        type="text"
      />
      <Textfield
        name="volume"
        label="Sauna volume"
        placeholder="1000"
        type="number"
      />

      <button class="btn btn-primary w-fit mt-5" type="submit"> Submit </button>
    </form>
    <div class="basis-2/3 my-10">
      <img
        class="mask mask-squircle"
        src="/src/images/picopump-order.png"
        alt="order something"
      />
    </div>
  </div>
</section>
<div class="toast toast-right toast-bottom hidden">
  <div class="alert alert-success">
    <span>PicoPump is soon on it's way</span>
  </div>
</div>

<style>
  /* Add any custom styles here */
  .show {
    display: block;
  }
</style>
