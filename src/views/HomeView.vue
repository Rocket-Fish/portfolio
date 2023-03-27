<script setup lang="ts">
import HomepageSection from "@/components/HomepageSection.vue";
import HeroSection from "@/components/homepage/HeroSection.vue";
</script>
<template>
  <main class="main">
    <HeroSection></HeroSection>
    <!-- <HomepageSection v-for="i in [1, 2, 3, 4, 5]" :key="i">
      <template #header>Some section {{ i }}</template>
      <template #default>
        <a href="#">link</a>
      </template>
    </HomepageSection> -->
  </main>
</template>
<style scoped>
.main {
  padding: 0 2rem;
}
</style>
