<script setup lang="ts">
import WhatIBring from "@/components/homepage/WhatIBring.vue";
import HeroSection from "@/components/homepage/HeroSection.vue";
import ProfessionalExperience from "@/components/homepage/ProfessionalExperience.vue";
import ContactMe from "@/components/homepage/ContactMe.vue";
import WaveSpacer from "@/components/homepage/WaveSpacer.vue";
</script>
<template>
  <main class="main">
    <HeroSection></HeroSection>
    <WhatIBring />
    <WaveSpacer />
    <ProfessionalExperience />
    <WaveSpacer :inverted="true" />
    <ContactMe />
  </main>
</template>
<style scoped>
.main {
  padding: 0;
}
</style>
