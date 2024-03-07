<script>
  export let amount;
  export let rating;

  const ratingPercentage = Math.round((rating % 1) * 100);
    
  const stars = Array.from({ length: rating }, (_, i) => i + 1);
</script>

<div class="flex items-center justify-center gap-2 text-base">
  <p>{rating}</p>

  {#each stars as star}
    <div class="grid place-items-center relative">
      <i class="fa-solid fa-star opacity-0"></i>
      <div
        class={"absolute top-0 left-0 grid place-items-center " +
          (star === Math.floor(rating)
            ? `w-[${ratingPercentage}%] overflow-hidden`
            : "")}
      >
        <i class="fa-solid fa-star text-amber-400"></i>
      </div>
    </div>
  {/each}

  {#if amount}
    <p>{amount}+ reviews</p>
  {/if}
</div>
