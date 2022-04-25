<script lang="ts">
  import logotype from "./assets/dymium-logotype.svg";
  console.log(logotype);
</script>

<main>
  <h1>Dymium</h1>
  <img src={logotype} alt="dymium logotype" />
  <div class="filter" />
  <div class="dymium-animation-root">
    <div class="circles-container-top">
      <div class="dymium-circle" />
      <div class="dymium-circle" />
      <div class="dymium-circle" />
      <div class="dymium-circle" />
      <div class="dymium-circle" />
      <div class="dymium-circle" />
      <div class="dymium-circle" />
    </div>
    <div class="circles-container-bottom">
      <div class="dymium-circle" />
      <div class="dymium-circle" />
      <div class="dymium-circle" />
      <div class="dymium-circle" />
      <div class="dymium-circle" />
      <div class="dymium-circle" />
      <div class="dymium-circle" />
    </div>
  </div>
  <div class="overlay-content">
    <a
      alt="Dymium contact mail"
      class="dymium-button-link"
      href="mailto:info@dymium.com">Get in touch</a
    >
  </div>
</main>

<style lang="scss">
  @keyframes fadeIn {
    0% {
      transform: scale(0.5);
      opacity: 0;
    }

    60% {
      opacity: 1;
      transform: scale(1.2);
    }

    100% {
      transform: scale(1);
    }
  }

  @keyframes energy {
    $color: rgba(255, 255, 255, 0.5);

    0% {
      filter: drop-shadow(1 0 10px $color) drop-shadow(0 0 1px $color)
        drop-shadow(0 1 2px $color);
    }

    100% {
      filter: drop-shadow(0 0 25px $color) drop-shadow(0 0 5px $color)
        drop-shadow(0 0 2px $color);
    }
  }
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
    background: linear-gradient(-5deg, #18719a 50%, #de5a13 50%);
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

  .dymium-animation-root {
    height: 100vh;
    width: 100vw;
    position: absolute;
    top: 0;
    left: 0;
    transform: rotateZ(-105deg);

    .circles-container-top,
    .circles-container-bottom {
      height: 50%;
      display: flex;
      justify-content: center;
      align-items: center;
    }
  }

  .circles-container-bottom {
    background: linear-gradient(180deg) bottom;
  }

  @mixin circle-size($size) {
    height: $size + 0px;
    width: $size + 0px;
  }

  .dymium-circle {
    position: absolute;
    border-radius: 50%;
    border-style: solid;
    border-color: white;
    mix-blend-mode: overlay;
    border-width: 3px;
    animation-fill-mode: both;
    animation: energy 1s 500ms alternate 2;
    transform: skewX(-25deg) rotateZ(-15deg);
    will-change: filter;
    &:nth-child(1) {
      @include circle-size(100);
      margin: 5px 0;
    }

    &:nth-child(2) {
      margin: 4px 0;
      @include circle-size(200);
    }

    &:nth-child(3) {
      margin: 3px 0;
      @include circle-size(300);
    }

    &:nth-child(4) {
      margin: 2px 0;
      @include circle-size(500);
    }

    &:nth-child(5) {
      margin: 1px 0;
      @include circle-size(800);
    }

    &:nth-child(6) {
      @include circle-size(1300);
    }

    &:nth-child(7) {
      margin: -1px 0;
      @include circle-size(4000);
    }
  }

  .circles-container-top .dymium-circle {
    bottom: 50%;
    transform-origin: bottom;
  }
  .circles-container-bottom .dymium-circle {
    transform-origin: top;
    top: 50%;
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

  img {
    position: absolute;
    top: auto;
    left: auto;
    bottom: auto;
    right: auto;
    width: 32vmax;
  }
  img,
  a.dymium-button-link {
    will-change: opacity, transform;
    animation: fadeIn 800ms 1.5s ease-in both;
  }

  img,
  .overlay-content {
    z-index: 3;
  }

  a:visited {
    text-decoration: none;
  }

  a.dymium-button-link,
  button {
    animation-delay: 2s;
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
    border: 1px rgba(255, 255, 255, 0.747) solid;
    border-radius: 4px;
  }

  h1,
  a {
    z-index: 1;
  }

  @media only screen and (max-width: 400px) {
    .dymium-circle {
      animation-delay: 1500ms;
    }

    img {
      animation-delay: 500ms;
    }

    a.dymium-button-link {
      animation-delay: 1000ms;
    }

    .overlay-content {
      margin-bottom: 208px;
    }
  }
</style>
