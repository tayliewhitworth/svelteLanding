<script>
  import Ctas from "./Ctas.svelte";
  import Header from "./Header.svelte";
  import SectionWrapper from "./SectionWrapper.svelte";
  import Stars from "./Stars.svelte";
</script>

<SectionWrapper id="">
  <Header />
  <div
    class="flex flex-col gap-10 flex-1 items-center justify-center pb-10 md:pb-14"
  >
    <h2
      class="text-5xl sm:texy-6xl md:text-7xl lg:text-8xl max-w-[1200px] mx-auto w-full text-center text-slate-600 font-semibold"
    >
      <span class="text-cyan-800">Revamp</span> Your Life With Our
      <span class="text-cyan-800">Help</span>
    </h2>
    <p
      class="text-xl sm:text-2xl md:text-3xl lg:text-4xl max-w-[1000px] mx-auto w-full text-center text-slate-400"
    >
      We have the best flooring in town. Reach out to us for a free consultation
      or browse our products below.
    </p>
    <Ctas />
    <Stars rating={4.6} amount={100} />
    <!-- <div class="flex items-center justify-center gap-2 text-base">
      <p>4.6</p>
      {#each [0, 1, 2, 3, 4] as star}
        <div class="grid place-items-center relative">
          <i class="fa-solid fa-star opacity-0"></i>
          <div
            class={"absolute top-0 left-0 grid place-items-center " +
              (star === 4 ? "w-[60%] overflow-hidden" : "")}
          >
            <i class="fa-solid fa-star text-amber-400"></i>
          </div>
        </div>
      {/each}
      <p>100+ reviews</p>
    </div> -->
  </div>
</SectionWrapper>
