<script setup lang="ts">
export type Card = {
  title: string;
  subtitle: string;
  description: string;
  isPrimary?: boolean;
};

defineProps({
  cards: Array<Card>,
});
</script>
<template>
  <div class="card-grid">
    <div
      class="card"
      v-for="card in cards"
      :key="card.title"
      :class="{ 'card-grid__primary': card.isPrimary }"
    >
      <h3 class="heading--s">{{ card.title }}</h3>
      <h4 class="body-m semi-bold">{{ card.subtitle }}</h4>
      <p class="body-m card-grid__description">{{ card.description }}</p>
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
    minmax(max(256px, calc(100% - 2rem) / 3), 1fr)
  );
  gap: 1rem;
}

.card-grid > .card {
  min-height: 250px;
}
@media (min-width: 592px) {
  .card-grid__primary {
    grid-column: span 2;
  }
}

.card-grid__description {
  min-height: 5rem;
}
</style>
