<script setup lang="ts">
import { RouterView } from "vue-router";
import NavBar from "./components/navbar/NavBar.vue";
</script>

<template>
  <NavBar />
  <RouterView />
  <footer class="footer">Copyright 2023 Jimmy, all rights reserved</footer>
</template>

<style scoped>
.footer {
  display: flex;
  justify-content: center;

  width: 100%;
}
</style>
