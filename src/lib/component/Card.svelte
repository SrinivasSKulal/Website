<script lang="ts">
  let link = $props();
</script>

<a class="card" href={link.source} target="_blank">
  <h3>{link.title}</h3>
  <p>{link.summary}</p>
</a>

<style>
  .card {
    display: flex;
    flex-direction: column;
    justify-content: center;

    width: 80%;
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
      width: 95%;
      padding: 15px;
    }

    h3 {
      font-size: 22px;
    }
  }
</style>
