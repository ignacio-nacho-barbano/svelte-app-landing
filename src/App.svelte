<script lang="ts">
  export let name: string;
</script>

<main>
  <h1>Dymium</h1>
  <div class="dymium-animation-root">
    <div class="circles-container-top">
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
    </div>
  </div>
  <div class="overlay-content">
    <h2>The future of data security is coming</h2>
    <a
      alt="Dymium contact mail"
      class="dymium-button-link"
      href="mailto:info@dymium.com">Get in touch</a
    >
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
    background: linear-gradient(
      260deg,
      #18234b 0%,
      #123d8b 20%,
      #5d85cd 50%,
      #e47253 50%,
      #dd4920 80%,
      #89250a 100%
    );
  }

  .dymium-animation-root {
    height: 100vh;
    width: 100vw;
    position: absolute;
    top: 0;
    left: 0;
    transform: rotateZ(-10deg);

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

  @keyframes circlesSpin {
    0% {
      transform: rotateZ(0deg);
    }
    100% {
      transform: rotateZ(360deg);
    }
  }

  @mixin circle-size($size) {
    height: $size + 0px;
    width: $size + 0px;
  }

  @keyframes pulse {
    0% {
      transform: scale(1);
    }

    30% {
      transform: scale(.9);
    }

    100% {
      transform: scale(1.1);
    }
  }

  @keyframes energy {
    0% {
      border-color: rgba(255, 255, 255, 0.623);
    }

    100% {
      border-color: rgba(255, 255, 255, 0.267);
    }
  }

  .dymium-circle {
    margin: -1px;
    position: absolute;
    border-radius: 50%;
    border-style: solid;
    border-color: rgba(255, 255, 255, 0.623);
    border-width: 1px;
	animation-fill-mode: both;
  	animation: pulse 3s infinite alternate, energy 1s infinite alternate;
    &:nth-child(0) {
      @include circle-size(100);
	  animation-delay: 100ms;
    }

    &:nth-child(1) {
      @include circle-size(200);
	  animation-delay: 200ms;
    }

    &:nth-child(2) {
      @include circle-size(300);
	  animation-delay: 300ms;
    }

    &:nth-child(3) {
      @include circle-size(500);
	  animation-delay: 500ms;
    }

    &:nth-child(4) {
      @include circle-size(800);
	  animation-delay: 800ms;
    }

    &:nth-child(5) {
      @include circle-size(1300);
	  animation-delay: 1300ms;
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

  h1,
  h2 {
    text-shadow: 1px 1px 0 rgba(58, 58, 58, 0.671);
  }

  .overlay-content {
    position: absolute;
    bottom: 0;
    margin-bottom: 104px;
    padding: 0 40px;
  }

  h1 {
    font-family: "Roboto";
    margin: auto;
    text-transform: uppercase;
    font-size: 5em;
    font-weight: 300;
  }

  h2 {
    font-size: 2rem;
    margin-bottom: 40px;
  }

  h1,
  h2,
  .overlay-content {
    z-index: 1;
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
    padding: 8px;
    font-weight: bold;
    backdrop-filter: blur(8px);
    color: white;
    border: 1px rgba(255, 255, 255, 0.747) solid;
    border-radius: 4px;
  }

  h1,
  h2,
  a {
    z-index: 1;
  }

  @media only screen and (max-width: 400px) {
    h1 {
      font-size: 3rem;
    }

    h2 {
      font-size: 1rem;
    }

    .overlay-content {
      margin-bottom: 208px;
    }
  }
</style>
