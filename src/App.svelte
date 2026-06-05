<script lang="ts">
  import Router, { link, router } from 'svelte-spa-router'
  import Home from './pages/Home.svelte'
  import About from './pages/About.svelte'
  import Contact from './pages/Contact.svelte'
  import Topbar from './components/Topbar.svelte'
  import Footer from './components/Footer.svelte'

  import { fly } from 'svelte/transition'
  import { cubicOut } from 'svelte/easing'
  
  const routes = {
    '/': Home,
    '/about': About,
    '/contact': Contact,
  }
</script>

<div class="app">
  <div class="waveBackground" aria-hidden="true">
    <svg preserveAspectRatio="none" viewBox="0 0 1440 400" xmlns="http://www.w3.org/2000/svg">
      <path class="wave1" d="M0 80 Q120 20 240 80 T480 80 T720 80 T960 80 T1200 80 T1440 80 T1680 80 T1920 80 T2160 80 T2400 80 T2640 80 T2880 80" fill="none" stroke="rgba(255,255,255,0.05)" stroke-width="1.5" />
      <path class="wave2" d="M0 140 Q120 80 240 140 T480 140 T720 140 T960 140 T1200 140 T1440 140 T1680 140 T1920 140 T2160 140 T2400 140 T2640 140 T2880 140" fill="none" stroke="rgba(255,255,255,0.035)" stroke-width="1.2" />
      <path class="wave3" d="M0 200 Q120 140 240 200 T480 200 T720 200 T960 200 T1200 200 T1440 200 T1680 200 T1920 200 T2160 200 T2400 200 T2640 200 T2880 200" fill="none" stroke="rgba(255,255,255,0.025)" stroke-width="1" />
      <path class="wave4" d="M0 260 Q120 200 240 260 T480 260 T720 260 T960 260 T1200 260 T1440 260 T1680 260 T1920 260 T2160 260 T2400 260 T2640 260 T2880 260" fill="none" stroke="rgba(255,255,255,0.015)" stroke-width="0.8" />
      <path class="wave5" d="M0 320 Q120 260 240 320 T480 320 T720 320 T960 320 T1200 320 T1440 320 T1680 320 T1920 320 T2160 320 T2400 320 T2640 320 T2880 320" fill="none" stroke="rgba(255,255,255,0.01)" stroke-width="0.6" />
    </svg>
  </div>
  <Topbar />
  <div class="pageWrapper">
    {#key router.location}
      <main
        class="mainContent"
        in:fly={{ y: 40, duration: 200, easing: cubicOut, opacity: 0 }}
        out:fly={{ y: 40, duration: 200, opacity: 0 }}
      >
        <Router {routes} />
      </main>
    {/key}
  </div>
  <Footer />
</div>

<style>
  .app {
    display: flex;
    flex-direction: column;
    min-height: 100vh;
  }

  .pageWrapper {
    position: relative;
    flex: 1;
  }

  @keyframes waveScroll {
    0% { transform: translateX(0); }
    100% { transform: translateX(-1440px); }
  }

  .waveBackground {
    position: fixed;
    inset: 0;
    z-index: -1;
    overflow: hidden;
    opacity: 0.6;

    & svg {
      width: 100%;
      height: 100%;
    }

    & .wave1 { animation: waveScroll 22s linear infinite; }
    & .wave2 { animation: waveScroll 20s linear infinite; }
    & .wave3 { animation: waveScroll 18s linear infinite; }
    & .wave4 { animation: waveScroll 16s linear infinite; }
    & .wave5 { animation: waveScroll 14s linear infinite; }
  }

  .mainContent {
    position: absolute;
    inset: 0;
    width: 100%;
    max-width: 720px;
    margin: 0 auto;
    padding: 64px 24px 48px;
    overflow-y: auto;
  }
</style>
