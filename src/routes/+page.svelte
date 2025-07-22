<script lang="ts">
  import { fade, slide } from 'svelte/transition';
  import { InView } from 'svelte-intersection-observer';

  let inViewHero = false;
  let inViewAbout = false;
  let inViewServices = false;
  let inViewPortfolio = false;
  let inViewContact = false;
</script>

<section class="hero bg-blue-600 text-white py-20 text-center">
  <InView bind:inView={inViewHero} rootMargin="-10% 0%">
    <div class="container mx-auto px-6" in:fade={inViewHero ? { delay: 200, duration: 800 } : {}}>
      <h1 class="text-5xl font-bold mb-4">Your Company: Innovate, Create, Inspire</h1>
      <p class="text-xl mb-8">
        We are a leading company dedicated to delivering exceptional solutions and services.
      </p>
      <a
        href="/services"
        class="bg-white text-blue-600 px-8 py-3 rounded-full text-lg font-semibold hover:bg-gray-100 transition-colors duration-300"
      >
        Our Services
      </a>
    </div>
  </InView>
</section>

<section class="about-overview py-16 bg-gray-100">
  <InView bind:inView={inViewAbout} rootMargin="-10% 0%">
    <div class="container mx-auto px-6 text-center" in:fade={inViewAbout ? { delay: 200, duration: 800 } : {}}>
      <h2 class="text-4xl font-bold text-gray-800 mb-8">Who We Are</h2>
      <p class="text-lg text-gray-700 max-w-3xl mx-auto">
        At Your Company, we believe in pushing boundaries and creating impactful experiences. Our team of dedicated professionals is committed to excellence and innovation in every project we undertake.
      </p>
      <a href="/about" class="mt-8 inline-block text-blue-600 hover:underline">Learn More About Us</a>
    </div>
  </InView>
</section>

<section class="services-overview py-16">
  <InView bind:inView={inViewServices} rootMargin="-10% 0%">
    <div class="container mx-auto px-6 text-center" in:fade={inViewServices ? { delay: 200, duration: 800 } : {}}>
      <h2 class="text-4xl font-bold text-gray-800 mb-8">What We Do</h2>
      <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
        <div class="service-card bg-white p-8 rounded-lg shadow-lg" in:slide={inViewServices ? { delay: 400, duration: 600 } : {}}>
          <h3 class="text-2xl font-semibold text-gray-800 mb-4">Web Development</h3>
          <p class="text-gray-700">Building responsive and high-performance web applications.</p>
        </div>
        <div class="service-card bg-white p-8 rounded-lg shadow-lg" in:slide={inViewServices ? { delay: 600, duration: 600 } : {}}>
          <h3 class="text-2xl font-semibold text-gray-800 mb-4">Mobile Apps</h3>
          <p class="text-gray-700">Creating intuitive and engaging mobile experiences for iOS and Android.</p>
        </div>
        <div class="service-card bg-white p-8 rounded-lg shadow-lg" in:slide={inViewServices ? { delay: 800, duration: 600 } : {}}>
          <h3 class="text-2xl font-semibold text-gray-800 mb-4">UI/UX Design</h3>
          <p class="text-gray-700">Crafting beautiful and user-friendly interfaces.</p>
        </div>
      </div>
      <a href="/services" class="mt-12 inline-block bg-blue-600 text-white px-8 py-3 rounded-full text-lg font-semibold hover:bg-blue-700 transition-colors duration-300">View All Services</a>
    </div>
  </InView>
</section>

<section class="portfolio-overview py-16 bg-gray-100">
  <InView bind:inView={inViewPortfolio} rootMargin="-10% 0%">
    <div class="container mx-auto px-6 text-center" in:fade={inViewPortfolio ? { delay: 200, duration: 800 } : {}}>
      <h2 class="text-4xl font-bold text-gray-800 mb-8">Our Latest Work</h2>
      <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
        <div class="portfolio-item bg-white rounded-lg shadow-lg overflow-hidden" in:slide={inViewPortfolio ? { delay: 400, duration: 600 } : {}}>
          <img src="https://via.placeholder.com/400x250" alt="Project 1" class="w-full h-48 object-cover" />
          <div class="p-6">
            <h3 class="text-xl font-semibold text-gray-800 mb-2">Project Alpha</h3>
            <p class="text-gray-700">A cutting-edge web application for a tech startup.</p>
          </div>
        </div>
        <div class="portfolio-item bg-white rounded-lg shadow-lg overflow-hidden" in:slide={inViewPortfolio ? { delay: 600, duration: 600 } : {}}>
          <img src="https://via.placeholder.com/400x250" alt="Project 2" class="w-full h-48 object-cover" />
          <div class="p-6">
            <h3 class="text-xl font-semibold text-gray-800 mb-2">Mobile App Beta</h3>
            <p class="text-gray-700">An intuitive mobile app designed for seamless user experience.</p>
          </div>
        </div>
        <div class="portfolio-item bg-white rounded-lg shadow-lg overflow-hidden" in:slide={inViewPortfolio ? { delay: 800, duration: 600 } : {}}>
          <img src="https://via.placeholder.com/400x250" alt="Project 3" class="w-full h-48 object-cover" />
          <div class="p-6">
            <h3 class="text-xl font-semibold text-gray-800 mb-2">Design System Gamma</h3>
            <p class="text-gray-700">A comprehensive design system for a large enterprise.</p>
          </div>
        </div>
      </div>
      <a href="/portfolio" class="mt-12 inline-block text-blue-600 hover:underline">View All Projects</a>
    </div>
  </InView>
</section>

<section class="contact-cta py-16 bg-blue-600 text-white text-center">
  <InView bind:inView={inViewContact} rootMargin="-10% 0%">
    <div class="container mx-auto px-6" in:fade={inViewContact ? { delay: 200, duration: 800 } : {}}>
      <h2 class="text-4xl font-bold mb-4">Ready to Start Your Project?</h2>
      <p class="text-xl mb-8">Let's work together to bring your ideas to life.</p>
      <a
        href="/contact"
        class="bg-white text-blue-600 px-8 py-3 rounded-full text-lg font-semibold hover:bg-gray-100 transition-colors duration-300"
      >
        Contact Us
      </a>
    </div>
  </InView>
</section>
