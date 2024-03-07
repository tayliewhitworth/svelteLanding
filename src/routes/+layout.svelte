<script>
  import "../app.css";
  import Ctas from "../components/Ctas.svelte";
  import Footer from "../components/Footer.svelte";

  import { openModal } from "../store";

  let y;

  $: outerHeight = 0;

  function reroute(href) {
    openModal.update((n) => !n);
    window.location.href = href;

  }

</script>
{#if $openModal}
  <div class="fixed top-0 left-0 w-screen h-screen border-b bg-white z-50 flex flex-col gap-8 p-5 px-8 md:hidden">
    <div class="flex items-center justify-between gap-4 border-b pb-2">
      <h1 class="font-semibold"><span class="text-cyan-800">Revamp</span> Flooring</h1>
      <button class="outline-none border-none text-cyan-800" on:click={() => openModal.update((n) => !n)}>
        <i class="fa-solid fa-times text-lg"></i>
      </button>
    </div>
    <div class="flex flex-col gap-4 flex-1">
      <button on:click={() => reroute("#about")} class="border-none outline-none p-2 group duration-200 cursor-pointer text-left font-medium">
        <p class="duration-200 group-hover:pl-2 text-3xl">About <i class="fa-solid fa-chevron-right text-xl pl-4"></i></p>
      </button>
      <button on:click={() => reroute("#products")} class="border-none outline-none p-2 group duration-200 cursor-pointer text-left font-medium">
        <p class="duration-200 group-hover:pl-2 text-3xl">Products <i class="fa-solid fa-chevron-right text-xl pl-4"></i></p>
      </button>
      <button on:click={() => reroute("#reviews")} class="border-none outline-none p-2 group duration-200 cursor-pointer text-left font-medium">
        <p class="duration-200 group-hover:pl-2 text-3xl">Reviews <i class="fa-solid fa-chevron-right text-xl pl-4"></i></p>
      </button>
      <button on:click={() => reroute("#faqs")} class="border-none outline-none p-2 group duration-200 cursor-pointer text-left font-medium">
        <p class="duration-200 group-hover:pl-2 text-3xl">FAQS <i class="fa-solid fa-chevron-right text-xl pl-4"></i></p>
      </button>
    </div>
    <Ctas />
  </div>
{/if}
{#if y > outerHeight}
  <div class="fixed bottom-0 right-0 z-50 p-1 bg-white bg-opacity-80 rounded-tl-md shadow-md">
    <button class="outline-none border-none" on:click={() => window.scrollTo({ top: 0, behavior: "smooth" })}>
      <i class="fa-solid fa-chevron-up text-xl text-cyan-800"></i>
    </button>
  </div>
{/if}

<slot />
<Footer />
<svelte:window bind:scrollY={y} bind:outerHeight />
