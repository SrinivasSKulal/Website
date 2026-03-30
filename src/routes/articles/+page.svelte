<script lang="ts">
  import { art_list } from "./articles.js";
  import Card from "$lib/component/Card.svelte";
</script>

<div class="hero">
  <h1>Articles</h1>

  {#each art_list as item}
    <Card title={item.title} summary={item.summary} source={item.slug} />
  {/each}
</div>

<style>
  .hero {
    font-family: "Iosevka Charon Mono", monospace;

    display: flex;
    flex-direction: column;
    align-items: center;

    min-height: 100vh;
    background: radial-gradient(#0a192f, #1a0f2e);

    color: white;
    padding: 20px;
  }
</style>
