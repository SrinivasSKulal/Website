<script lang="ts">
  const links = [
    { name: "Home", href: "/" },
    { name: "Projects", href: "/projects" },
    { name: "Articles", href: "/articles" },
  ];

  let menuOpen = $state(false);
  const toggleMenu = () => (menuOpen = !menuOpen);
  const closeMenu = () => (menuOpen = false);
</script>

<header class="header">
  <h1 class="title">Srinivas's Personal Website 🏴‍☠️</h1>

  <!-- Desktop nav -->
  <nav class="desktop-nav">
    {#each links as link}
      <a href={link.href}>
        {link.name}
      </a>
    {/each}
  </nav>

  <!-- Hamburger button (mobile only) -->
  <button class="hamburger" onclick={toggleMenu} aria-label="Toggle menu">
    {#if menuOpen}
      ✕
    {:else}
      ☰
    {/if}
  </button>
</header>

<!-- Mobile dropdown -->
{#if menuOpen}
  <nav class="mobile-nav">
    {#each links as link}
      <a href={link.href} onclick={closeMenu}>
        {link.name}
      </a>
    {/each}
  </nav>
{/if}

<!-- Fonts -->
<link rel="preconnect" href="https://fonts.googleapis.com" />
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
<link
  href="https://fonts.googleapis.com/css2?family=Bitcount+Prop+Double:wght@100..900&family=Iosevka+Charon+Mono:ital,wght@0,300;0,400;0,500;0,700&display=swap"
  rel="stylesheet"
/>

<style>
  .header {
    display: flex;
    align-items: center;
    justify-content: space-between;
    background: linear-gradient(to bottom, #0077ff, #0d479f);
    font-family: "Bitcount Prop Double", monospace;
    font-size: 25px;
    font-weight: 500;
    color: #7fff00;
    padding: 15px 30px;
  }
  .title {
    margin: 0;
    font-size: 48px;
    font-weight: 500;
  }

  /* Desktop nav */
  .desktop-nav {
    display: flex;
    gap: 20px;
  }
  .desktop-nav a {
    color: white;
    text-decoration: none;
    padding: 6px 12px;
    border-radius: 6px;
    transition: 0.2s ease;
  }
  .desktop-nav a:hover {
    background: rgba(255, 255, 255, 0.2);
  }
  .desktop-nav a.active {
    background: white;
    color: #2a5298;
    font-weight: bold;
    box-shadow: 0 0 8px rgba(255, 255, 255, 0.6);
  }

  /* Hamburger button */
  .hamburger {
    display: none;
    background: none;
    border: 2px solid white;
    color: white;
    font-size: 22px;
    border-radius: 6px;
    padding: 4px 10px;
    cursor: pointer;
    line-height: 1;
  }

  /* Mobile nav dropdown */
  .mobile-nav {
    display: none;
    flex-direction: column;
    background: #0d479f;
    font-family: "Bitcount Prop Double", monospace;
    font-size: 20px;
  }
  .mobile-nav a {
    color: white;
    text-decoration: none;
    padding: 14px 24px;
    border-bottom: 1px solid rgba(255, 255, 255, 0.15);
    transition: background 0.2s ease;
  }
  .mobile-nav a:hover {
    background: rgba(255, 255, 255, 0.1);
  }
  .mobile-nav a.active {
    background: white;
    color: #2a5298;
    font-weight: bold;
  }

  @media (max-width: 768px) {
    .title {
      font-size: 28px;
    }
    .desktop-nav {
      display: none;
    }
    .hamburger {
      display: block;
    }
    .mobile-nav {
      display: flex;
    }
  }
</style>
