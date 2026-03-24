<script lang="ts">
  import { page } from "$app/stores";

  const links = [
    { name: "Home", href: "/" },
    { name: "Articles", href: "/articles" },
    { name: "Projects", href: "/projects" },
  ];
</script>

<header class="header">
  <h1 class="title">Srinivas's Personal Website 🏴‍☠️</h1>

  <nav>
    {#each links as link}
      <a href={link.href}>
        {link.name}
      </a>
    {/each}
  </nav>
</header>

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

  nav {
    display: flex;
    gap: 20px;
  }

  nav a {
    color: white;
    text-decoration: none;
    padding: 6px 12px;
    border-radius: 6px;
    transition: 0.2s ease;
  }

  nav a:hover {
    background: rgba(255, 255, 255, 0.2);
  }

  nav a.active {
    background: white;
    color: #2a5298;
    font-weight: bold;
    box-shadow: 0 0 8px rgba(255, 255, 255, 0.6);
  }
</style>
