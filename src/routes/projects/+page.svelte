<script>
  import Card from "$lib/component/Card.svelte";

  import { items } from "./projects.js";
</script>

<div class="hero">
  Here are a list of projects :

  {#each items as item}
    <!-- content here -->

    <Card
      title={item.title}
      summary={item.summary}
      source={item.source}
      image={item.image}
      github={item.github}
    />
  {/each}
</div>

<style>
  .hero {
    font-family: "Iosevka Charon Mono", monospace;
    font-size: 30px;

    display: flex;
    flex-direction: column;
    align-items: center;

    min-height: 100vh; /* 🔥 important */
    background: radial-gradient(#0a192f, #1a0f2e);

    color: white;
  }
  h1 {
    font-size: 36px;
    padding-top: 10vh;
    text-align: center;
  }

  p {
    font-size: 20px;
    padding: 10vh;
  }
</style>
