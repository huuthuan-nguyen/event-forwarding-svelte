<script>
  import Product from "./Product.svelte";
  const products = [
    {
      id: "p1",
      title: "A book",
      price: 9.99,
    },
  ];
</script>

{#each products as product}
  <Product
    {...product}
    on:add-to-cart={() => alert("Add to cart!")}
    on:delete={() => alert("Delete!")}
  />
{/each}
