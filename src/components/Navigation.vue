<template>
  <nav>
    <router-link to="/"><span>Home</span></router-link> |
    <router-link to="/contact"><span>Find me here</span></router-link>
  </nav>
</template>

<style scoped lang="scss">
nav {
  padding: 30px;
}
a:hover:not(.router-link-active) {
  color: var(--background);
}
</style>