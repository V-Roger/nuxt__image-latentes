<template>
  <div class="app-wrapper">
    <nuxt />
  </div>
</template>

<style lang="scss" scoped>
  html,
  body {
    margin: 0;
    padding: 0;
    min-height: 100vh;
    width: 100vw;
    font-family: 'Lato', sans-serif;
    color: #5a5a5a;
  }

  *,
  *:before,
  *:after {
    box-sizing: border-box;
  }

  .app-wrapper {
    padding: 8px;
    border: 24px solid #212529;
  }
</style>
