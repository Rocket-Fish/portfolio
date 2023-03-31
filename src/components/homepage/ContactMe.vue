<script setup lang="ts">
import TestimonialGrid from "./TestimonialGrid.vue";
import type { Testimonial } from "./TestimonialGrid.vue";
import { ref } from "vue";
const testimonials = ref<Testimonial[]>([
  // {
  //   name: "Name",
  //   role: "Current Role",
  //   description:
  //     "Say something nice; Lorem Ipsum is simply dummy text of the printing and typesetting industry. ",
  //   linkedInUrl: "#",
  // },
  // {
  //   name: "Name",
  //   role: "Current Role",
  //   description:
  //     "Say something nice; Lorem Ipsum is simply dummy text of the printing and typesetting industry. ",
  //   linkedInUrl: "#",
  // },
  // {
  //   name: "Name",
  //   role: "Current Role",
  //   description:
  //     "Say something nice; Lorem Ipsum is simply dummy text of the printing and typesetting industry. ",
  //   linkedInUrl: "#",
  //   primary: true,
  // },
  {
    name: "Jaclyn Ling",
    role: "CEO @Hatchways",
    description:
      "I met Jimmy at the beginning of his career when he was looking for his first software position. What struck me was how motivated and hardworking he was. He is the type of person who will put 110% in. Over the years, I've seen him grow a stronger product sense with an interest in design and user experience. Any team would be lucky to have Jimmy on the team!",
    linkedInUrl: "#",
    primary: true,
  },
]);
</script>
<template>
  <section class="section container contact-me">
    <div class="left">
      <h3 class="heading--xs">
        I am currently looking to contribute to interesting projects.
      </h3>
      <h2 class="heading--xxl">Don't Delay, <br />Connect Today</h2>
      <a
        class="button"
        target="_blank"
        href="https://www.linkedin.com/in/jimmy-z-096b031b2/"
        >Connect & Chat on LinkedIn →</a
      >
    </div>
    <div class="right">
      <TestimonialGrid :testimonials="testimonials" />
    </div>
  </section>
</template>
<style scoped>
.contact-me {
  display: flex;
  justify-content: space-between;
  flex-wrap: wrap;
  flex-direction: row;
  align-items: center;

  gap: 3rem;
}
.left {
  display: flex;
  flex-direction: column;
  align-items: flex-start;

  gap: 1rem;
}

.right {
  display: flex;
  flex-direction: column;
  gap: 1rem;
}

@media (min-width: 1280px) {
  .right {
    max-width: 600px;
  }
}
</style>
