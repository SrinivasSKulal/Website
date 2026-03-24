<script lang="ts">
  import favicon from "$lib/assets/favicon.svg";
  import Header from "$lib/component/Header.svelte";
  import Sidebar from "$lib/component/Sidebar.svelte";
  let { children } = $props();
</script>

<svelte:head>
  <link rel="icon" href={favicon} />
</svelte:head>

<div class="app">
  <Header />
  <div class="main">
    <Sidebar />
    <div class="content">
      {@render children()}
    </div>
  </div>
</div>

<style>
  :global(html, body) {
    margin: 0;
    padding: 0;
  }
  .app {
    display: flex;
    flex-direction: column;
    margin: 0;
    width: 100%;
    padding: 0;
    height: 100vh;
  }

  .main {
    display: flex;
    flex: 1;
  }

  .content {
    flex: 1;
    border: solid black 3px;
  }
</style>
