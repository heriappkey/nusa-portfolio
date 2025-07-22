<script lang="ts">
  import { fade, slide } from 'svelte/transition';
  import { InView } from 'svelte-intersection-observer';

  let inViewPortfolioHeader = false;
  let inViewPortfolioItems = [
    false, false, false, false, false, false
  ];
</script>

<section class="py-16">
  <div class="container mx-auto px-6">
    <InView bind:inView={inViewPortfolioHeader} rootMargin="-10% 0%">
      <h1 class="text-5xl font-bold text-gray-800 mb-8 text-center" in:fade={inViewPortfolioHeader ? { delay: 200, duration: 800 } : {}}>Our Portfolio</h1>
    </InView>
    <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
      {#each [0, 1, 2, 3, 4, 5] as i}
        <InView bind:inView={inViewPortfolioItems[i]} rootMargin="-10% 0%">
          <div class="portfolio-item bg-white rounded-lg shadow-lg overflow-hidden group" in:slide={inViewPortfolioItems[i] ? { delay: 200 + i * 100, duration: 600 } : {}}>
            <img src="https://via.placeholder.com/600x400" alt="Project {i + 1}" class="w-full h-64 object-cover transform group-hover:scale-105 transition-transform duration-500" />
            <div class="p-6">
              <h3 class="text-xl font-semibold text-gray-800 mb-2">
                {#if i === 0}Project Alpha{:else if i === 1}Mobile App Beta{:else if i === 2}Design System Gamma{:else if i === 3}E-commerce Platform{:else if i === 4}Data Analytics Dashboard{:else if i === 5}Branding & Identity{/if}
              </h3>
              <p class="text-gray-700">
                {#if i === 0}A cutting-edge web application for a tech startup, focusing on user experience and scalability.
                {:else if i === 1}An intuitive mobile app designed for seamless user experience on both iOS and Android platforms.
                {:else if i === 2}A comprehensive design system developed to ensure consistency and efficiency across all digital products.
                {:else if i === 3}A robust e-commerce solution with secure payment gateways and a user-friendly interface.
                {:else if i === 4}An interactive dashboard for visualizing complex data and gaining actionable insights.
                {:else if i === 5}Comprehensive branding and identity development for a new startup, including logo and guidelines.{/if}
              </p>
              <a href="#" class="text-blue-600 hover:underline mt-4 inline-block">View Details</a>
            </div>
          </div>
        </InView>
      {/each}
    </div>
  </div>
</section>
