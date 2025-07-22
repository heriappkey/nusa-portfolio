<script lang="ts">
  import { page } from '$app/stores';

  let currentPath: string;

  $: {
    currentPath = $page.url.pathname;
  }

  const navItems = [
    { name: 'Home', path: '/' },
    { name: 'About', path: '/about' },
    { name: 'Services', path: '/services' },
    { name: 'Portfolio', path: '/portfolio' },
    { name: 'Contact', path: '/contact' },
  ];
</script>

<header class="bg-white shadow-md py-4 px-6">
  <nav class="container mx-auto flex justify-between items-center">
    <a href="/" class="text-2xl font-bold text-gray-800">Your Company</a>
    <ul class="flex space-x-6">
      {#each navItems as item}
        <li>
          <a
            href={item.path}
            class="text-gray-600 hover:text-blue-600 transition-colors duration-300 {currentPath === item.path ? 'font-semibold text-blue-600' : ''}"
          >
            {item.name}
          </a>
        </li>
      {/each}
    </ul>
  </nav>
</header>
