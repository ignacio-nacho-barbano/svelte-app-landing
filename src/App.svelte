<script lang="ts">
  import logotype from "./assets/dymium-logotype.svg";
  import { fade } from "svelte/transition";

  let circlesVisible = false;
  setTimeout(() => {
    circlesVisible = true;
  }, 1000);
</script>

<main>
  <h1>Dymium</h1>
<video autoplay muted id="dymium-animated">
  <source src="./assets/dymium-animated-video.webm" type="video/webm">
  Your browser does not support HTML5 video.
</video>

  {#if false}
    <img
      class="logotype"
      transition:fade={{ duration: 400, delay: 5400 }}
      src={logotype}
      alt="dymium logotype"
    />
  {/if}

  <div class="overlay-content">
    {#if circlesVisible}
      <a
        transition:fade={{ delay: 2000, duration: 300 }}
        alt="Dymium contact mail"
        class="dymium-button-link"
        href="mailto:info@dymium.com">Get in touch</a
      >
    {/if}
  </div>
</main>

<style lang="scss">
  main {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    text-align: center;
    height: 100vh;
    width: 100vw;
    position: absolute;
    top: 0;
    overflow: hidden;
    left: 0;
  }

  video {
    position: absolute;
    top: 0;
    bottom: 0;
    left: 0;
    right: 0;
    width: 100vw;
    height: 100vh;
    object-fit: cover;
  }

  .overlay-content {
    position: absolute;
    bottom: 0;
    margin-bottom: 104px;
    padding: 0 40px;
  }

  h1 {
    visibility: hidden;
  }

  img.logotype {
    position: absolute;
    top: auto;
    left: auto;
    bottom: auto;
    right: auto;
    max-width: 67vmax;
  }

  img.logotype,
  .overlay-content {
    z-index: 3;
  }

  a:visited {
    text-decoration: none;
  }

  a.dymium-button-link,
  button {
    background: linear-gradient(
      rgba(0, 0, 0, 0.658),
      rgba(0, 0, 0, 0.507) 30%,
      rgba(0, 0, 0, 0.664)
    );
    padding: 12px 20px;
    font-weight: bold;
    backdrop-filter: blur(8px);
    color: white;
    font-size: 20px;
    line-height: 20px;
    border: 1px rgba(255, 255, 255, 0.747) solid;
    border-radius: 4px;
  }

  h1,
  a {
    z-index: 1;
  }

  @media only screen and (max-width: 600px) {

    main {
      background: linear-gradient(174deg, #fca62b 49.5%, #00a2d5 50.5%);
    }

    video {
      margin: auto;
      height: 120vmin;
    }


    a.dymium-button-link {
      font-size: 16px;
      line-height: 16px;
    }

    .overlay-content {
      margin-bottom: 30vh;
    }
  }
</style>
