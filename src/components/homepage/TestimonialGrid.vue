<script setup lang="ts">
export type Testimonial = {
  name: string;
  role: string;
  description: string;
  linkedInUrl: string;
  primary?: boolean;
};

defineProps({
  testimonials: Array<Testimonial>,
});
</script>
<template>
  <div class="card-grid">
    <div
      class="card"
      :class="{ primary: card.primary }"
      v-for="card in testimonials"
      :key="card.name"
    >
      <div class="card-container">
        <p class="body-m">{{ card.description }}</p>
        <h3 class="heading--xs">
          {{ card.name }}
        </h3>
        <h4 class="heading--xss normal">{{ card.role }}</h4>
      </div>
    </div>
  </div>
</template>
<style scoped>
.card-grid {
  width: 100%;
  max-width: 100%;
  display: grid;
  grid-template-columns: repeat(
    auto-fit,
    minmax(max(256px, calc(100% - 1rem) / 2), 1fr)
  );
  gap: 1rem;
}

.primary {
  grid-column: 1/-1;
}
</style>
