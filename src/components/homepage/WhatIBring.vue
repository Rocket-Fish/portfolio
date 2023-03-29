<script setup lang="ts">
import { ref } from "vue";
import CardGrid from "@/components/homepage/CardGrid.vue";
import type { Card } from "@/components/homepage/CardGrid.vue";

const cards = ref<Card[]>([
  {
    title: "Frontend Development",
    subtitle: "Vue, React, Web Components",
    description:
      "Turn designs into efficient, compliant, secure, and maintainable code. Experienced in creating complex dashboard and passwordless authentication experiences.",
    isPrimary: true,
  },
  {
    title: "UI/UX Design",
    subtitle: "Figma",
    description:
      "Develop ideas into user flows, compiling them into wireframes, and finalizing them into prototypes.",
  },
  {
    title: "Backend Development",
    subtitle: "Node, Express, Golang, Postgres",
    description:
      "Build lightning fast and secure API endpoints to support the best possible user experience.",
  },
  {
    title: "Product Deployment",
    subtitle: "Docker, Heroku, Gitlab CI/CD",
    description:
      "Adapt the product to build and deployment requirements whether it's containerization or CI/CD pipelines.",
  },
  {
    title: "Focus on Security",
    subtitle: "Try to break things",
    description:
      "How can I exploit what I'm building? Where are its attack surfaces? What strategies can I incorporate to prevent and mitigate damage.",
  },
]);
</script>
<template>
  <section class="section container" id="what-i-bring">
    <h2 class="heading--l">What I bring to the team</h2>
    <CardGrid :cards="cards" />
  </section>
</template>
