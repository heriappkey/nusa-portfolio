<script lang="ts">
  import "../app.css";
  import Header from "../lib/components/Header.svelte";
  import Footer from "../lib/components/Footer.svelte";
  import { fade } from 'svelte/transition';
  import { quintOut } from 'svelte/easing';
  import { page } from '$app/stores';

  let currentPath: string;
  $: currentPath = $page.url.pathname;
</script>

<div class="flex flex-col min-h-screen">
  <Header />
  <main class="flex-grow">
    {#key currentPath}
      <div in:fade={{ duration: 300, easing: quintOut }} out:fade={{ duration: 300, easing: quintOut }}>
        <slot />
      </div>
    {/key}
  </main>
  <Footer />
</div>
