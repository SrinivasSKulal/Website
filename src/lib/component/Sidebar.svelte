<script lang="ts">
  let points = Array(5);
</script>

<div class="sidebar">
  <h3>About Me</h3>
  <p>
    I love linxu (currently using Fedora 43) and CLI/TUI's . Sci-fi and Robots
    are what i dream about and Fallout and Gundam are few of my favourite
    series. I always appreciate things that can go boom
  </p>
  <h3>Contact Info</h3>
  <p>
    <b> Email</b>
    <br />srinivaskulalwork@gmail.com
    <b>Linkedin</b> <br />Link
  </p>
  <div class="container">
    <!-- Pole -->

    <div class="pole"></div>

    <!-- Flag grid -->
    <div class="flag">
      {#each points as _, i}
        <div class="square" style={`--i:${i}`}></div>
      {/each}

      {#each points as _, i}
        <div class="square" style={`--i:${i}`}></div>
      {/each}
    </div>
  </div>
</div>

<!-- <h3> </h3>  -->
<!-- <p> </p> -->

<style>
  .container {
    display: flex;
    align-items: flex-start;
    gap: 0px;
    padding-left: 20px;
  }
  .pole {
    background: green;
    height: 200px;
    width: 20px;
  }

  .flag {
    display: grid;
    grid-template-columns: repeat(5, 30px);
    grid-template-rows: repeat(2, 30px);
    gap: 0px;
  }

  .square {
    width: 30px;
    height: 30px;
    background: crimson;

    animation: sway 2s infinite ease-in-out;

    animation-delay: calc(var(--i) * 0.1s);
  }
  @media (min-width: 720p) {
    .sidebar {
      display: block;
    }
  }
  @keyframes sway {
    0% {
      transform: translatey(8px);
    }
    50% {
      transform: translatey(-8px);
    }
    100% {
      transform: translatey(8px);
    }
  }

  .sidebar {
    width: 250px;
    background: black;
    color: white;
    font-family: "iosevka charon mono", monospace;
    font-size: 20px;
  }

  h3 {
    background: #0077ff;
    width: 250px;
    text-align: center;
    color: white;
    padding: 0;
    margin: 0;
  }
  p {
    color: white;
    padding: 10px 10px;
  }
</style>
