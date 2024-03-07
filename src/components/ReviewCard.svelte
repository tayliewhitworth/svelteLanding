<script>
  import Stars from "./Stars.svelte";

  export let review;
  export let left;
  export let index;
</script>

<div
  class={"flex flex-col gap-2 w-full max-w-[500px] mx-auto relative " +
    (left
      ? index % 2 === 1
        ? " hidden md:flex opacity-0 pointer-events-none max-h-[40px] overflow-hidden"
        : " "
      : index % 2 == -0
        ? " hidden md:flex opacity-0 pointer-events-none max-h-[40px] overflow-hidden"
        : " ")}
>
  <div class="flex relative">
    <div
      class={"absolute rounded-full bg-white aspect-square hidden md:grid place-items-center h-4 top-0 " +
        (index % 2 === 0
          ? " right-0 -mr-8 translate-x-1/2"
          : " left-0 -ml-8 -translate-x-1/2")}
    >
      <div class="rounded-full bg-slate-950 aspect-square h-2"></div>
    </div>
  </div>
  <div class="flex items-center gap-2">
    <i class="fa-solid fa-user"></i>
    <h3 class="text-lg sm:text-xl md:text-2xl font-semibold">{review.name}</h3>
  </div>
  <div class="h-[1.5px] bg-slate-950 w-1/4 mr-auto mb-4 mt-2"></div>
  <div class="flex items-center flex-wrap gap-2 text-xs sm:text-sm mb-4">
    {#each review.features as feature}
      <div
        class="p-1 py-0.5 rounded-md border border-solid border-cyan-800 bg-slate-100 text-cyan-800"
      >
        <p>{feature}</p>
      </div>
    {/each}
  </div>
  <p class="text-slate-500">{review.review}</p>
  <Stars rating={review.stars} amount=""/>
</div>
