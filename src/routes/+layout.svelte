<script lang="ts">
  import "../app.css";
  import Header from "../lib/components/Header.svelte";
  import Footer from "../lib/components/Footer.svelte";
  import { fade } from 'svelte/transition';
  import { quintOut } from 'svelte/easing';
</script>

<div class="flex flex-col min-h-screen">
  <Header />
  <main class="flex-grow">
    {#key $page.url.pathname}
      <div in:fade={{ duration: 300, easing: quintOut }} out:fade={{ duration: 300, easing: quintOut }}>
        <slot />
      </div>
    {/key}
  </main>
  <Footer />
</div>
