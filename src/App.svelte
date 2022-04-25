<script lang="ts">
  import logotype from "./assets/dymium-logotype.svg";
  import circles from "./assets/circles.svg";
  import { fade } from "svelte/transition";

  let circlesVisible = false;
  let blurredCirclesVisible = false;
  setTimeout(() => {
    circlesVisible = true;
    blurredCirclesVisible = true;
  }, 400);

  setTimeout(() => {
    blurredCirclesVisible = false;
  }, 1500);
</script>

<main>
  <h1>Dymium</h1>
  {#if circlesVisible}
    <img
      class="logotype"
      transition:fade={{ duration: 400, delay: 1000 }}
      src={logotype}
      alt="dymium logotype"
    />
  {/if}
  <div class="filter" />

  {#if circlesVisible}
    <img class="dymium-circles" src={circles} alt="dymium logo circles" />
  {/if}

  {#if blurredCirclesVisible}
    <img
      class="dymium-circles with-blur"
      src={circles}
      alt="dymium logo circles"
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
  .filter,
  main {
    background: linear-gradient(-5deg, #18719a 49.9%, #de5a13 50.1%);
  }

  img.dymium-circles {
    position: absolute;
    object-fit: cover;
    width: 100vw;
    height: 100vh;
    left: 0;
    right: 0;
    top: 0;
    bottom: 0;

    &.with-blur {
      $color: rgba(255, 255, 255, 0.5);

      filter: drop-shadow(0 0 16px $color) drop-shadow(0 0 4px $color)
        drop-shadow(0 0 1px $color);
    }
  }

  .filter {
    z-index: 2;
    position: absolute;
    left: 0;
    top: 0;
    right: 0;
    bottom: 0;
    mix-blend-mode: hard-light;
    opacity: 0.8;
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
    max-width: 40vmax;
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

  @media only screen and (max-width: 400px) {
    a.dymium-button-link {
      font-size: 16px;
      line-height: 16px;
    }
  }
</style>
