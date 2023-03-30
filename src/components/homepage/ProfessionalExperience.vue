<script setup lang="ts">
import { ref } from "vue";
import CardGrid from "@/components/homepage/CardGrid.vue";
import type { Card } from "@/components/homepage/CardGrid.vue";

const loginIDProjects = ref<Card[]>([
  {
    title: "Core Passwordless Authentication and Identity Product",
    subtitle: "Vue, Lit(Web Components), Typescript, Golang, Postgres, Docker",
    description:
      "Design, develop, and test FIDO2 based passwordless authentication experiences and identity verification solutions for all three user interfaces in this product: an administrator dashboard, an OIDC authentication experience, and a dashboard for the end user. Collaborate with team members on features, updates, and fixes.",
    isPrimary: true,
    button: {
      label: "Learn more",
      to: "https://loginid.io/products",
    },
  },
  {
    title: "Public Documentation",
    subtitle: "React, Docusaurus, Strapi, Redoc, Terraform",
    description:
      "Architect, develop, and deploy a public documentation site that must be editable by non technical people and generate beautiful API docs.",
    button: {
      label: "See docs",
      to: "https://docs.loginid.io",
    },
  },
  {
    title: "Main Website",
    subtitle: "Vue, Nuxt.js, Strapi, Prosemirror, Terraform",
    description:
      "Architect and develop the company's main marketing website, collaborate with the marketing team to update and refine the experience.",
    button: {
      label: "View product",
      to: "https://loginid.io",
    },
  },
  {
    title: "Wordpress Plugin",
    subtitle: "PHP",
    description:
      "Architect, develop, and published a wordpress plugin integrated with LoginID's FIDO2 passwordless authentication API. ",
    button: {
      label: "Plugin page",
      to: "https://en-ca.wordpress.org/plugins/loginid-directweb/",
    },
  },
  {
    title: "Technical Demos",
    subtitle: "Node, Typescript, PHP, Python, and others",
    description:
      "Contribute to development various demos for a variety of audiences ranging from clients, customers, or stakeholders.",
    button: {
      label: "See example",
      to: "https://github.com/loginid1/nodejs-express-integration",
    },
  },
]);

const personalProjects = ref<Card[]>([
  {
    title: "fish-bot",
    subtitle:
      "Express, Postgres, Knex, Discord API, FFlogs API, GraphQL, Docker",
    description:
      "A configurable discord bot that could automatically assign any discord role to any user which fulfills a programmable set of requirements based on the user's FFlogs rankings. There are other bots that does something similar, however, fish-bot relies heavily on discord's interaction api, requiring no external dashboards.",
    isPrimary: true,
    button: {
      label: "Source code",
      to: "https://github.com/Rocket-Fish/fish-bot",
    },
  },
  {
    title: "An E-Commerce Site",
    subtitle: "React, Redux, Express, Stripe, Firebase",
    description:
      "A dummy full stack e-commerce site built using React and Express with Stripe integration for payment processing. Firebase for their nosql database.",
    button: {
      label: "Github link",
      to: "https://github.com/Rocket-Fish/Totally-Not-An-E-Commerce-Site",
    },
  },
  {
    title: "Babl",
    subtitle: "React, Redux, Express, Google Translate",
    description:
      "A simple facebook messenger clone with automatic translation of messages.",
    button: {
      label: "View project",
      to: "https://github.com/hatchways/team-mint-oreo",
    },
  },
  {
    title: "Endless Nights",
    subtitle: "Java, LibGDX, OpenGL, GPGS",
    description:
      "A simple 2D game about firing arrows in the dark. Integrated with Google Play Games Service.",
    button: {
      label: "Source code",
      to: "https://github.com/Rocket-Fish/Endless-Nights",
    },
  },
  {
    title: "Robotics Programing",
    subtitle: "@FRC Team 1246",
    description:
      "Back in 2017, I wrote some code for my highschool robotics team. Looking back many things could be done better, including but not limited to using better sensors and more automation for complex mechanisms to reduce the burden on the pilot.",
  },
]);
</script>
<template>
  <div class="professional-experience">
    <section class="section container">
      <h2 class="heading--l">Professional & Personal Experience</h2>
      <p class="body--m">
        Three years of professional experience; Ten years of coding and
        counting.
      </p>
      <article class="work-experience">
        <header>
          <h3 class="heading--m">
            Frontend Engineer
            <a href="https://loginid.io" target="_blank">@LoginID</a>
          </h3>
          <h4 class="heading--xss">March 2020 - Present</h4>
          <p class="body--m">
            Architect, design, develop, test, and maintain frontend interfaces
            across various products.
            <br />
            Coordinate with other engineering team members on implementation,
            architecture, and deployment. As well as perform reviews of other
            team member's code
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
          <h3 class="heading--m">Personal Projects</h3>
          <h4 class="heading--xss">2014 - Present</h4>
        </header>
        <CardGrid :cards="personalProjects" />
      </article>
    </section>
  </div>
</template>
<style scoped>
.professional-experience {
  background-color: var(--c-primary-800);
}
.work-experience {
  width: 100%;

  display: flex;
  flex-direction: column;
  gap: 1rem;
}
</style>
