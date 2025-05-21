<template>
  <header class="header">
    <SiteTitle class="d-none d-md-block" />
    <SiteTitleMobile class="d-md-none" />
    <div class="overlay bg-gradient" />
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
    padding-top: calc(9rem + 2vh);
    background: var(--orange) url(../assets/images/background.jpg);
    background-size: auto 100%;
    animation: HeaderOrange 180s linear infinite;
    overflow: clip;

    &:deep(svg) {
      width: 100%;
      max-width: 1450px;
      position: relative;
      z-index: 10;
    }

    .overlay {
      position: absolute;
      inset: 0;
      mix-blend-mode: multiply;
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
    }
  }
</style>