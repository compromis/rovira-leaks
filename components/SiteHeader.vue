<template>
  <header class="header bg-gradient">
    <slot />
  </header>
</template>

<style lang="scss" scoped>
  .header {
    display: flex;
    justify-content: center;
    margin: 0 0 2rem;
    border-bottom-right-radius: 2rem;
    border-bottom-left-radius: 2rem;
    padding: calc(1rem + 2vh);
    padding-top: calc(9rem + 2vh);


    &:deep(svg) {
      width: 100%;
      max-width: 1450px;
    }
  }
</style>