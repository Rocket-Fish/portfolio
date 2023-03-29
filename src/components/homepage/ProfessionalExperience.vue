<script setup lang="ts">
import { ref } from "vue";
import CardGrid from "@/components/homepage/CardGrid.vue";
import type { Card } from "@/components/homepage/CardGrid.vue";

const loginIDProjects = ref<Card[]>([
  {
    title: "Core Passwordless Authentication and Identity Product",
    subtitle: "Vue, Lit(Web Components), Typescript, Golang, Postgres, Docker",
    description: "TODO: talk about this",
    isPrimary: true,
  },
  {
    title: "Public Documentation",
    subtitle: "React, Docusaurus, Strapi, Redoc, Terraform",
    description: "TODO: talk about this",
  },
  {
    title: "Main Website",
    subtitle: "Vue, Nuxt.js, Strapi, Prosemirror, Terraform",
    description: "TODO: talk about this",
  },
  {
    title: "Wordpress Plugin",
    subtitle: "PHP",
    description: "TODO: talk about this",
  },
  {
    title: "Technical Demos",
    subtitle: "Node, Typescript, PHP, Python, and others",
    description: "TODO: talk about this",
  },
]);

const personalProjects = ref<Card[]>([
  {
    title: "fish-bot",
    subtitle:
      "Express, Postgres, Knex, Discord API, FFlogs API, GraphQL, Docker",
    description: "TODO: talk about this",
    isPrimary: true,
  },
  {
    title: "An E-Commerce Site",
    subtitle: "React, Redux, Express, Stripe, Firebase",
    description: "TODO: talk about this",
  },
  {
    title: "Babl",
    subtitle: "React, Redux, Express, Mongo, Sockets",
    description: "TODO: talk about this",
  },
  {
    title: "Endless Nights",
    subtitle: "Java, LibGDX, OpenGL, GPGS",
    description: "TODO: talk about this",
  },
  {
    title: "Robotics Programming",
    subtitle: "Java, First Robotics Competition",
    description: "TODO: talk about this",
  },
]);
</script>
<template>
  <section class="section container">
    <h2 class="heading--l">Professional & Personal Experience</h2>
    <p>
      Three years of professional experience; Ten years of coding and counting.
    </p>
    <article class="work-experience">
      <header>
        <h3 class="heading--m">
          Frontend Engineer @
          <a href="https://loginid.io" target="_blank">LoginID</a>
        </h3>
        <h4 class="heading--xss">March 2020 - Present</h4>
        <p class="body--m">
          Architect, design, develop, test, and maintain frontend interfaces
          across various products.
          <br />
          Coordinate with other engineering team members on implementation,
          architecture, and deployment. As well as perform reviews of other team
          member's code
          <br />
          Collaborate with various executives, product managers, and other
          stakeholders to develop and refine user experiences.
          <br />
          LoginID was built around the following core technologies:
          <a
            href="https://auth0.com/intro-to-iam/what-is-openid-connect-oidc"
            target="_blank"
            >OIDC</a
          >,
          <a
            href="https://developer.mozilla.org/en-US/docs/Web/API/Web_Authentication_API"
            target="_blank"
            >Webauthn API</a
          >,
          <a href="https://fidoalliance.org/fido2/" target="_blank">FIDO2</a>,
          <a
            href="https://en.wikipedia.org/wiki/Public_key_infrastructure"
            target="_blank"
            >PKI</a
          >
        </p>
      </header>
      <CardGrid :cards="loginIDProjects" />
    </article>
    <article class="work-experience">
      <header>
        <h3 class="heading--m">Programming Enthusiast</h3>
        <h4 class="heading--xss">2014 - Present</h4>
        <p class="body--m">Some personal projectsI had done over the years</p>
      </header>
      <CardGrid :cards="personalProjects" />
    </article>
  </section>
</template>
<style scoped>
.work-experience {
  width: 100%;

  display: flex;
  flex-direction: column;
  gap: 1rem;
}
</style>
