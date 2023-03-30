<script setup lang="ts">
defineProps({
  to: String,
  description: String,
});
</script>
<template>
  <a :href="to" target="_blank" class="animated-link">
    <span class="moveable-text">
      {{ description }}
    </span>
    <span class="icon">
      <slot></slot>
    </span>
  </a>
</template>
<style scoped>
.animated-link {
  display: flex;
  justify-content: end;
  gap: 0.5rem;

  text-decoration: none;

  width: 100%;
  transition: 0.4s ease-in-out, width 0.9s ease-in-out;
}

html:not([data-scroll="0"]) .nav {
  background: var(--color-background);
}
.moveable-text {
  overflow: hidden;
  transition: width 1s ease-in-out;
  width: 100%;
}

html:not([data-scroll="0"]) .moveable-text {
  width: 0px;
}
html:not([data-scroll="0"]) .animated-link {
  width: 1.5rem;
}

@media screen and (prefers-reduced-motion: reduce) {
  .animated-link,
  .moveable-text {
    transition: 0s;
  }
}
</style>
