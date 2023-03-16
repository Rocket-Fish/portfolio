<script setup lang="ts">
import { RouterLink } from "vue-router";
</script>
<template>
  <nav>
    <RouterLink to="/" class="prevent-default-hover">
      <img class="logo" src="/icon.svg" />
    </RouterLink>
  </nav>
</template>
<style scoped>
nav {
  padding: 1rem 2rem;
  position: sticky;
  top: 0;
  z-index: 100;
  background: var(--color-background);
}

nav img.logo {
  height: 50px;
  width: auto;
}
</style>
