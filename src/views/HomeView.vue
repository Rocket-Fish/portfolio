<script setup lang="ts">
import HomepageSection from "@/components/HomepageSection.vue";
</script>

<template>
  <main>
    <h1>Launching your <b>Something</b></h1>
    <HomepageSection v-for="i in [1, 2, 3, 4, 5]" :key="i">
      <template #header>Some section {{ i }}</template>
    </HomepageSection>
  </main>
</template>
