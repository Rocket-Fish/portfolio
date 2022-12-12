<script setup lang="ts"></script>
<template>
  <section>
    <h2>
      <slot name="header"></slot>
    </h2>
  </section>
</template>
<style scoped>
section {
  min-height: 100vh;
}
</style>
