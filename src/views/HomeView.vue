<script setup lang="ts">
import HomepageSection from "@/components/HomepageSection.vue";
import Hero from "@/components/homepage/Hero.vue";
</script>
<template>
  <main>
    <Hero></Hero>
    <HomepageSection v-for="i in [1, 2, 3, 4, 5]" :key="i">
      <template #header>Some section {{ i }}</template>
    </HomepageSection>
  </main>
</template>
<style scoped>
main {
  padding: 0 2rem;
}
</style>
