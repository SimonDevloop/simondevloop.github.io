<script>
  import { link, router } from 'svelte-spa-router'

  const pages = [
    { page: 'Home', url: '/' },
    { page: 'About', url: '/about' },
    { page: 'Contact', url: '/contact' },
  ]

  let currentPage = $derived(router.location)
</script>

<nav class="topbar">
  <a href="/" use:link class="logo" style="display: flex; align-items: center;">
    <img width=45 height=45 src="/images/simonidle.png" alt="Simon Idle" style="filter: brightness(300%);"/>
    Simon
  </a>
  <div class="navLinks">
    {#each pages as { page, url }}
      <a
        href={url}
        use:link
        class:activeLink={currentPage === url}
        class:inactiveLink={currentPage !== url}
      >
        {page}
      </a>
    {/each}
  </div>
</nav>

<style>
  .topbar {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 16px 24px;
    border-bottom: 1px solid rgba(255, 255, 255, 0.06);
    background-color: rgba(10, 10, 10, 0.8);
    backdrop-filter: blur(12px);
    position: sticky;
    top: 0;
    z-index: 10;

    & .logo {
      font-size: 20px;
      font-weight: 600;
      letter-spacing: -0.02em;
      text-decoration: none;
    }

    & .navLinks {
      display: flex;
      gap: 24px;

      & a {
        font-size: 14px;
        font-weight: 400;
        letter-spacing: 0.02em;
        text-transform: uppercase;
        transition: color 0.2s ease;
        text-decoration: none;
      }

      & .activeLink {
        color: #ffffff;
        font-weight: 500;
      }

      & .inactiveLink {
        color: rgba(255, 255, 255, 0.45);

        &:hover {
          color: rgba(255, 255, 255, 0.8);
        }
      }
    }
  }
</style>
