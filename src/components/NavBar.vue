<script setup lang="ts">
import { RouterLink } from "vue-router";
import IconGithub from "@/components/icons/IconGithub.vue";
import IconLinkedin from "@/components/icons/IconLinkedin.vue";
</script>
<template>
  <nav class="nav">
    <div class="nav__container container">
      <RouterLink
        to="/"
        class="prevent-default-hover"
        aria-label="Go back to the homepage by clicking the logo"
      >
        <img class="logo" src="/logo2.svg" alt="logo" />
      </RouterLink>
      <div class="icon-container">
        <a href="" target="_blank">
          <IconLinkedin />
        </a>
        <a href="" target="_blank">
          <IconGithub />
        </a>
      </div>
    </div>
  </nav>
</template>
<style scoped>
.nav {
  padding: 1rem 2rem;
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  z-index: 100;
  background: transparent;
}

.nav__container {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.nav img.logo {
  height: 50px;
  width: 50px;
}

.nav .icon-container {
  display: flex;
  gap: 1rem;
}
</style>
