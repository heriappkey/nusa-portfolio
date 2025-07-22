<script lang="ts">
  import { fade, slide } from 'svelte/transition';
  import { InView } from 'svelte-intersection-observer';

  let inViewServicesHeader = false;
  let inViewServiceCards = [
    false, false, false, false, false, false
  ];
</script>

<section class="py-16">
  <div class="container mx-auto px-6">
    <InView bind:inView={inViewServicesHeader} rootMargin="-10% 0%">
      <h1 class="text-5xl font-bold text-gray-800 mb-8 text-center" in:fade={inViewServicesHeader ? { delay: 200, duration: 800 } : {}}>Our Services</h1>
    </InView>
    <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
      {#each [0, 1, 2, 3, 4, 5] as i}
        <InView bind:inView={inViewServiceCards[i]} rootMargin="-10% 0%">
          <div class="service-card bg-white p-8 rounded-lg shadow-lg text-center" in:slide={inViewServiceCards[i] ? { delay: 200 + i * 100, duration: 600 } : {}}>
            <div class="text-blue-600 mb-4">
              {#if i === 0}
                <svg xmlns="http://www.w3.org/2000/svg" class="h-16 w-16 mx-auto" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M10 20l4-16m4 4l4 4-4 4M6 16l-4-4 4-4" />
                </svg>
              {:else if i === 1}
                <svg xmlns="http://www.w3.org/2000/svg" class="h-16 w-16 mx-auto" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 18h.01M8 21h8a2 2 0 002-2V5a2 2 0 00-2-2H8a2 2 0 00-2 2v14a2 2 0 002 2z" />
                </svg>
              {:else if i === 2}
                <svg xmlns="http://www.w3.org/2000/svg" class="h-16 w-16 mx-auto" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9.663 17h4.673M12 3v18" />
                  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19.813 17.525c-1.222 1.222-2.83 1.975-4.525 1.975H9.663c-1.695 0-3.303-.753-4.525-1.975L2 12l3.138-5.525C6.36 5.253 7.968 4.5 9.663 4.5h4.673c1.695 0 3.303.753 4.525 1.975L22 12l-3.187 5.525z" />
                </svg>
              {:else if i === 3}
                <svg xmlns="http://www.w3.org/2000/svg" class="h-16 w-16 mx-auto" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 6V4m0 2a2 2 0 100 4m0-4a2 2 0 110 4m-6 8a2 2 0 100-4m0 4a2 2 0 110-4m0 4v2m0-6V4m6 6v10m6-2a2 2 0 100-4m0 4a2 2 0 110-4m0 4v2m0-6V4" />
                </svg>
              {:else if i === 4}
                <svg xmlns="http://www.w3.org/2000/svg" class="h-16 w-16 mx-auto" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 3v4M3 5h4M6 17v4m-2-2h4m5-16l2.286 6.857L21 12l-5.714 2.143L12 21l-2.286-6.857L3 12l5.714-2.143L12 3z" />
                </svg>
              {:else if i === 5}
                <svg xmlns="http://www.w3.org/2000/svg" class="h-16 w-16 mx-auto" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M8 9l3 3-3 3m5 0h3M5 20h14a2 2 0 002-2V6a2 2 0 00-2-2H5a2 2 0 00-2 2v12a2 2 0 002 2z" />
                </svg>
              {/if}
            </div>
            <h2 class="text-2xl font-semibold text-gray-800 mb-4">
              {#if i === 0}Web Development{:else if i === 1}Mobile App Development{:else if i === 2}UI/UX Design{:else if i === 3}Digital Marketing{:else if i === 4}Cloud Solutions{:else if i === 5}IT Consulting{/if}
            </h2>
            <p class="text-gray-700">
              {#if i === 0}We build modern, responsive, and high-performance websites tailored to your business needs. From simple landing pages to complex web applications, we deliver solutions that drive results.
              {:else if i === 1}Reach your audience on the go with custom mobile applications for iOS and Android. We focus on intuitive user experiences and robust functionality to bring your ideas to life.
              {:else if i === 2}We craft intuitive and visually appealing user interfaces and experiences. Our design process focuses on user research, wireframing, prototyping, and testing to ensure optimal usability and engagement.
              {:else if i === 3}Boost your online presence and reach your target audience with our comprehensive digital marketing strategies, including SEO, social media marketing, and content creation.
              {:else if i === 4}Leverage the power of the cloud with our expert cloud consulting and implementation services. We help you migrate, manage, and optimize your infrastructure for scalability and efficiency.
              {:else if i === 5}Get expert advice and strategic guidance on your technology initiatives. We help you make informed decisions to optimize your IT infrastructure and achieve your business objectives.{/if}
            </p>
          </div>
        </InView>
      {/each}
    </div>
  </div>
</section>
