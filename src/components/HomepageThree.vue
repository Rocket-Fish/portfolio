<script setup lang="ts">
import { ref } from "vue";

const scrollProgress = ref(0);
</script>
<template>
  <span class="scroll-progress">Scroll Progress: {{ scrollProgress }}</span>
</template>
<style scoped>
.scroll-progress {
  position: fixed;
  bottom: 10px;
  left: 10px;
  z-index: 99;
  font-size: 3vh;
}
</style>
