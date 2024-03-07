<script>
  import ReviewCard from "./ReviewCard.svelte";
  import SectionWrapper from "./SectionWrapper.svelte";

  let lim = true;

  let reviewsList = [
    {
      name: "John Doe",
      review:
        "Swoley Moley has been a game-changer for my fitness journey! The personalized workout plans and progress tracking tools are amazing, and the community keeps me motivated. I especially love the feature that recommends new workouts based on my goals and strengths.",
      features: [
        "Personalized workout plans",
        "Community features",
        "Workout recommendation system",
      ],
      stars: 4.7,
    },
    {
      name: "Jane Smith",
      review:
        "Swoley Moley is the most user-friendly fitness app I've ever used. The interface is clean and intuitive, and the exercises are easy to follow. I've already seen significant results in just a few weeks. My favorite features are the guided workouts and the ability to log my meals and track my progress.",
      features: [
        "Guided workouts",
        "Meal logging and tracking",
        "User-friendly interface",
      ],
      stars: 3.6,
    },
    {
      name: "Michael Brown",
      review:
        "Swoley Moley is the best investment I've made in my health. It's helped me build muscle, lose weight, and improve my overall fitness level. The variety of workout routines and challenges keeps me engaged, and the nutrition tips are super helpful. I highly recommend this app to anyone looking to get in shape!",
      features: [
        "Variety of workout routines and challenges",
        "Nutrition tips",
        "Progress tracking and challenges",
      ],
      stars: 4.9,
    },
    {
      name: "Sarah Williams",
      review:
        "I'm a busy mom of two, and Swoley Moley has been a lifesaver! It helps me fit in quick and effective workouts even when I'm short on time. I love the timer feature that keeps me on track, and the workout variety ensures I never get bored.",
      features: [
        "Quick and effective workouts",
        "Timer feature",
        "Variety of workouts",
      ],
      stars: 4.2,
    },
    {
      name: "David Lee",
      review:
        "As a seasoned athlete, I was skeptical about any fitness app. But Swoley Moley has surprised me! It offers advanced workout programs and allows me to customize my routines to fit my specific needs. The data analysis is fantastic, helping me track my progress and optimize my performance.",
      features: [
        "Advanced workout programs",
        "Customization options",
        "Detailed data analysis",
      ],
      stars: 4.8,
    },
    {
      name: "Ashley Johnson",
      review:
        "Swoley Moley has helped me overcome my fear of going to the gym. The encouraging community and supportive environment have made me feel comfortable and confident. I love the social features that allow me to connect with other fitness enthusiasts and share my progress.",
      features: [
        "Supportive community",
        "Social features",
        "Encouraging environment",
      ],
      stars: 4.5,
    },
    {
      name: "Mark Robinson",
      review:
        "Swoley Moley is more than just a fitness app; it's a lifestyle change. It's helped me develop healthy habits and make better choices about my diet and exercise. I'm incredibly grateful for this app and the positive impact it's had on my life.",
      features: [
        "Focus on healthy habits",
        "Nutritional guidance",
        "Positive lifestyle impact",
      ],
      stars: 4.6,
    },
  ];
</script>

<SectionWrapper id="reviews">
  <div
    class="flex flex-col gap-10 sm:gap-14 md:gap-24 py-20 flex-1 items-center justify-center"
  >
    <div class="flex flex-col gap-2">
      <p class="text-base sm:text-lg md:text-xl text-center opacity-60">
        Don't just take our word for it
      </p>
      <h3
        class="text-4xl sm:text-5xl md:text-6xl text-center font-semibold max-w-[1000px] mx-auto w-full"
      >
        See What <span class="text-cyan-800">Our Customers</span> Are Saying
      </h3>
    </div>
    <div class="flex flex-col md:flex-row gap-8 w-fit mx-auto">
      <div class="flex flex-col gap-8">
        {#each lim ? reviewsList.slice(0, 4) : reviewsList as review, index}
          <ReviewCard {review} left={true} {index} />
        {/each}
      </div>
      <div class="w-[1px] bg-slate-950 hidden md:flex"></div>
      <div class="flex flex-col gap-8">
        {#each lim ? reviewsList.slice(0, 4) : reviewsList as review, index}
          <ReviewCard {review} left={false} {index} />
        {/each}
      </div>
    </div>
    <button on:click={() => (lim = !lim)} class="specialBtn">
      {lim ? "Show More" : "Show Less"}
    </button>
  </div>
</SectionWrapper>
