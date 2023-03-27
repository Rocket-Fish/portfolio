<script setup lang="ts"></script>
<template>
  <section class="section">
    <h2>
      <slot name="header"></slot>
    </h2>
    <p>
      <slot></slot>
    </p>
  </section>
</template>
<style scoped>
.section {
  min-height: 100vh;
}
</style>
