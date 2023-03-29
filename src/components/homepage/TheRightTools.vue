<script setup lang="ts">
import { ref } from "vue";

type Tool = {
  icon: URL; // see https://vitejs.dev/guide/assets.html
  name: string;
};
const toolsList = ref<Tool[]>([
  {
    name: "Vue",
    icon: new URL("@/assets/img/Vue.svg", import.meta.url),
  },
]);
</script>
<template>
  <section class="section container">
    <h2 class="heading--l">Using the right tools for your product</h2>
    <p>
      Every tool comes at a cost, whether in time, money, performance, or
      developer experience.
      <br />
      With an ever growing amount of new tools released every year, it is
      imperative to use the right tools to tackle the challenges in a product.
      <br />
      I have experience or am familiar with the following tools
    </p>
    <div class="tools-list">
      <div class="tool-card" v-for="tool in toolsList" :key="tool.name">
        <img :src="tool.icon.href" :alt="`${tool.name} icon`" />
        <p class="body-s">{{ tool.name }}</p>
      </div>
    </div>
  </section>
</template>
<style scoped>
.tools-list {
  display: flex;

  width: 100%;

  gap: 0.5rem;
  flex-wrap: wrap;
}

.tool-card {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;

  width: 128px;
  height: 128px;

  transition: 0.4s ease-in-out;
  filter: grayscale(1);
}

.tool-card img {
  width: 64px;
  height: 64px;
}

@media (hover: hover) {
  .tool-card:hover {
    filter: grayscale(0);
  }
}
</style>
