<script>
    let items = [
        { name: "PicoPump Standard", price: 10 },
        { name: "PicoPump Plus", price: 20 },
        { name: "PicoPump Extreme", price: 30 },
    ];
    // @ts-ignore
    /**
   * @type {any[]}
   */
    let selectedItems = [];
    let total = 0;

    // @ts-ignore
    function addToCart(item) {
        // @ts-ignore
        selectedItems = [...selectedItems, item];
        total += item.price;
    }

    // @ts-ignore
    function removeFromCart(item) {
        // @ts-ignore
        selectedItems = selectedItems.filter((i) => i !== item);
        total -= item.price;
    }
</script>

<main class="p-4">
    <h1 class="text-2xl font-bold mb-4">Order Page</h1>

    <div class="grid grid-cols-3 gap-4">
        {#each items as item}
            <div class="bg-white rounded-lg shadow p-4">
                <h2 class="text-lg font-bold mb-2">{item.name}</h2>
                <p class="text-gray-500">${item.price}</p>
                <button
                    class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded mt-4"
                    on:click={() => addToCart(item)}
                >
                    Add to Cart
                </button>
            </div>
        {/each}
    </div>

    <div class="mt-8">
        <h2 class="text-lg font-bold mb-2">Cart</h2>
        {#if selectedItems.length === 0}
            <p>Your cart is empty.</p>
        {:else}
            <ul class="list-disc pl-4">
                {#each selectedItems as item}
                    <li class="mb-2">
                        {item.name} - ${item.price}
                        <button
                            class="bg-red-500 hover:bg-red-700 text-white font-bold py-1 px-2 rounded ml-4"
                            on:click={() => removeFromCart(item)}
                        >
                            Remove
                        </button>
                    </li>
                {/each}
            </ul>
            <p class="mt-4 font-bold">Total: ${total}</p>
        {/if}
    </div>
</main>

<style>
    /* Add any custom styles here */
</style>
