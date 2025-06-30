<template>
  <header class="header">
    <div class="header-grid">
      <SiteTitle class="d-none d-md-block header-title" />
      <SiteTitleMobile class="d-md-none header-title" />
      <div class="comegamba">
        <img src="../assets/images/comegamba.png" alt="Rovira amb un pitet amb una llagosta" />
      </div>
    </div>
    <div class="overlay" />
  </header>
</template>

<style lang="scss" scoped>
  .header {
    position: relative;
    display: flex;
    justify-content: center;
    margin: 0 0 2rem;
    border-bottom-right-radius: 2rem;
    border-bottom-left-radius: 2rem;
    padding: calc(1rem + 2vh);
    padding-top: calc(5rem + 2vh);
    padding-bottom: 0;
    background: #0056a4 url(../assets/images/background.jpg);
    background-size: auto 100%;
    animation: HeaderOrange 180s linear infinite;
    overflow: clip;

    &:deep(svg) {
      width: 100%;
      max-width: 1450px;
    }

    .overlay {
      position: absolute;
      inset: 0;
      mix-blend-mode: multiply;
      background-color: #0056a4;
    }

    &-grid {
      position: relative;
      z-index: 10;
      display: grid;
      grid-template-columns: 3fr 1fr 1fr;
      align-items: center;
      width: 100%;
      max-width: 1500px;
    }

    &-title {
      grid-area: 1 / 1 / 2 / 4;
    }

    .comegamba {
      grid-area: 1 / 3 / 2 / 4;
      height: calc(35vh + 4rem);
      display: flex;

      img {
        height: 100%;
      }
    }
  }

  @keyframes HeaderOrange {
    0%   { background-position:0% 50%; }
    50%  { background-position:100% 50%; }
    100% { background-position:0% 50%; }
  }

  @include media-breakpoint-down(md) { 
    .header {
      border-bottom-right-radius: 1rem;
      border-bottom-left-radius: 1rem;
      padding-inline: 1rem;
      padding-block-start: 10rem;
      padding-block-end: 5rem;

      .comegamba {
        display: none;
      }
    }
  }
</style>