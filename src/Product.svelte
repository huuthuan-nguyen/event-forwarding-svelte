<script>
    import { createEventDispatcher } from "svelte";
    export let title;
    export let price;
    export let bestseller = false;
    export let id;
    const dispatch = createEventDispatcher();

    function addToCart(event) {
        console.log(event);
        dispatch("add-to-cart");
    }

    function deleteProduct(event) {
        console.log(event);
        dispatch("delete");
    }
</script>

<article>
    <h1>{title}</h1>
    <h2>${price}</h2>
    {#if bestseller}
        <h3>{bestseller}</h3>
    {/if}
    <button on:click={addToCart}>Add to cart</button>
    <button on:click={deleteProduct}>Delete</button>
</article>
