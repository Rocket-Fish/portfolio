<script setup lang="ts">
import { RouterView } from "vue-router";
import NavBar from "./components/navbar/NavBar.vue";
import { computed } from "vue";

const currentYear = computed(() => new Date().getFullYear());
</script>

<template>
  <NavBar />
  <RouterView />
  <footer class="footer">
    Copyright 2023 - {{ currentYear }} Jimmy, all rights reserved
  </footer>
</template>

<style scoped>
.footer {
  display: flex;
  justify-content: center;

  width: 100%;
  padding-bottom: 1rem;
}
</style>
