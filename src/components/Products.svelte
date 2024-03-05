<script>
  import ProductCard from "./ProductCard.svelte";
  import SectionWrapper from "./SectionWrapper.svelte";
  let productFeatures = [
    {
      title: "Earthen Bottle",
      price: "$48",
      image:
        "https://tailwindui.com/img/ecommerce-images/category-page-04-image-card-01.jpg",
    },
    {
      title: "Nomad Tumbler",
      price: "$35",
      image:
        "https://tailwindui.com/img/ecommerce-images/category-page-04-image-card-02.jpg",
    },
    {
      title: "Focus Paper Refill",
      price: "$89",
      image:
        "https://tailwindui.com/img/ecommerce-images/category-page-04-image-card-03.jpg",
    },
    {
      title: "Machined Mechanical Pencil",
      price: "$35",
      image:
        "https://tailwindui.com/img/ecommerce-images/category-page-04-image-card-04.jpg",
    },
  ];
</script>

<SectionWrapper id="products">
  <div class="flex flex-col items-center gap-4">
    <h2 class="text-4xl font-bold text-cyan-800">Products</h2>
    <div class="bg-white">
      <div
        class="mx-auto max-w-2xl px-4 py-16 sm:px-6 sm:py-24 lg:max-w-7xl lg:px-8"
      >
        <h2 class="sr-only">Products</h2>

        <div
          class="grid grid-cols-1 gap-x-6 gap-y-10 sm:grid-cols-2 lg:grid-cols-3 xl:grid-cols-4 xl:gap-x-8"
        >
          <!-- Product 1 -->
          {#each productFeatures as product}
            <ProductCard {product} />
          {/each}

          <!-- More products... -->
        </div>
      </div>
    </div>
  </div>
</SectionWrapper>
