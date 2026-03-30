<script lang="ts">
  let link = $props();
</script>

<a class="card" href={link.source} target="_blank">
  {#if link.image}
    <img src={link.image} alt={link.summary} />
  {/if}
  <h3>{link.title}</h3>
  <p>{link.summary}</p>
</a>
{#if link.github}
  <a class="github" target="_blank" href={link.github}>Github</a>
{/if}

<style>
  img {
    width: 100%;
    height: 180px;
    object-fit: cover;
    border-radius: 8px;
    margin-bottom: 10px;
  }
  .github {
    margin-top: 10px;
    align-self: flex-start;
    background: #7fff00;
    color: black;
    padding: 6px 12px;
    border-radius: 6px;
    text-decoration: none;
    font-weight: bold;
    margin: 20px auto;
  }

  .github:hover {
    background: #5cff00;

    margin: 20px auto;
  }
  .card {
    display: flex;
    flex-direction: column;
    justify-content: center;

    width: 70%;
    margin: 20px auto;
    padding: 20px;

    border-radius: 12px;

    background: #0a192f;
    color: white;

    text-decoration: none;

    transition: all 0.25s ease;
    border: 1px solid rgba(0, 119, 255, 0.2);
  }

  .card:hover {
    transform: translateY(-5px);
    background: #0077ff;
    box-shadow: 0 10px 25px rgba(0, 119, 255, 0.4);
  }

  h3 {
    margin: 0;
    font-size: 28px;
    color: #7fff00;
  }

  p {
    margin-top: 10px;
    font-size: 16px;
    color: #e6f0ff;
  }

  /* 📱 Mobile */
  @media (max-width: 720px) {
    .card {
      width: 75%;
    }

    h3 {
      font-size: 22px;
    }
  }
</style>
