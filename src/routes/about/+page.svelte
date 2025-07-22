<script lang="ts">
  import { fade, slide } from 'svelte/transition';
  import { InView } from 'svelte-intersection-observer';

  let inViewAboutContent = false;
  let inViewVision = false;
  let inViewTeam = false;
</script>

<section class="py-16">
  <div class="container mx-auto px-6">
    <h1 class="text-5xl font-bold text-gray-800 mb-8 text-center">About Us</h1>
    <InView bind:inView={inViewAboutContent} rootMargin="-10% 0%">
      <div class="max-w-4xl mx-auto text-lg text-gray-700 leading-relaxed" in:fade={inViewAboutContent ? { delay: 200, duration: 800 } : {}}>
        <p class="mb-6">
          Welcome to Your Company, where innovation meets excellence. We are a passionate team dedicated to delivering cutting-edge solutions that empower businesses and individuals alike. Founded in [Year],
          our journey began with a simple yet powerful vision: to transform ideas into reality through technology and creativity.
        </p>
        <p class="mb-6">
          Our mission is to provide unparalleled services in web development, mobile application creation, and UI/UX design. We believe in a collaborative approach, working closely with our clients to understand their unique needs and deliver tailored solutions that exceed expectations.
        </p>
      </div>
    </InView>

    <InView bind:inView={inViewVision} rootMargin="-10% 0%">
      <div class="max-w-4xl mx-auto text-lg text-gray-700 leading-relaxed" in:fade={inViewVision ? { delay: 200, duration: 800 } : {}}>
        <h2 class="text-3xl font-bold text-gray-800 mb-4 mt-10">Our Vision</h2>
        <p class="mb-6">
          To be a global leader in digital solutions, recognized for our innovation, quality, and unwavering commitment to client success.
        </p>
      </div>
    </InView>

    <InView bind:inView={inViewTeam} rootMargin="-10% 0%">
      <div class="max-w-4xl mx-auto text-lg text-gray-700 leading-relaxed" in:fade={inViewTeam ? { delay: 200, duration: 800 } : {}}>
        <h2 class="text-3xl font-bold text-gray-800 mb-4 mt-10">Our Team</h2>
        <p class="mb-6">
          Behind every successful project is a dedicated team. Our experts bring a diverse range of skills and experiences, united by a shared passion for technology and a commitment to continuous learning and improvement.
        </p>
        <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8 mt-8">
          <div class="team-member bg-white p-6 rounded-lg shadow-lg text-center" in:slide={inViewTeam ? { delay: 400, duration: 600 } : {}}>
            <img src="https://via.placeholder.com/150" alt="Team Member 1" class="w-32 h-32 rounded-full mx-auto mb-4 object-cover" />
            <h3 class="text-xl font-semibold text-gray-800">John Doe</h3>
            <p class="text-blue-600">CEO & Founder</p>
          </div>
          <div class="team-member bg-white p-6 rounded-lg shadow-lg text-center" in:slide={inViewTeam ? { delay: 600, duration: 600 } : {}}>
            <img src="https://via.placeholder.com/150" alt="Team Member 2" class="w-32 h-32 rounded-full mx-auto mb-4 object-cover" />
            <h3 class="text-xl font-semibold text-gray-800">Jane Smith</h3>
            <p class="text-blue-600">Lead Developer</p>
          </div>
          <div class="team-member bg-white p-6 rounded-lg shadow-lg text-center" in:slide={inViewTeam ? { delay: 800, duration: 600 } : {}}>
            <img src="https://via.placeholder.com/150" alt="Team Member 3" class="w-32 h-32 rounded-full mx-auto mb-4 object-cover" />
            <h3 class="text-xl font-semibold text-gray-800">Peter Jones</h3>
            <p class="text-blue-600">UI/UX Designer</p>
          </div>
        </div>
      </div>
    </InView>
  </div>
</section>
