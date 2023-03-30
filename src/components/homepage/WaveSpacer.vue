<script setup lang="ts">
defineProps({
  inverted: Boolean,
});
</script>
<template>
  <div class="spacer" :class="{ inverted: inverted }"></div>
</template>
<style scoped>
.spacer {
  aspect-ratio: 900/200;
  width: 100%;
  background-repeat: no-repeat;
  background-position: center;
  background-size: cover;

  background-image: url("@/assets/img/layered-waves-haikei.svg");
}

.wave-svg {
  width: 100%;
  height: 100%;
}

.inverted {
  transform: rotate(180deg);
  background-image: url("@/assets/img/layered-waves-haikei-2.svg");
}
</style>
