<script setup lang="ts">
import LavaLamp from "./LavaLamp.vue";
import IconGithub from "@/components/icons/IconGithub.vue";
import IconLinkedin from "@/components/icons/IconLinkedin.vue";
</script>
<template>
  <section class="hero">
    <div class="hero__background">
      <LavaLamp />
    </div>
    <div class="hero__layout container">
      <div class="hero-card card card--large card--transparent">
        <div class="card-container">
          <p class="body body-m semi-bold hero-description">
            Hi, I'm Jimmy, I am a
          </p>
          <h1 class="hero-heading heading heading--xxl">
            Software Engineer<br />& More
          </h1>
          <p class="body body-m semi-bold hero-description">
            I build intuitive, secure, and performant web apps.
          </p>
          <div class="hero-card__cta">
            <a href="#what-i-bring" class="button">Learn more</a>
            <!-- <div class="hero-card__icon-container">
            <a
              href="https://www.linkedin.com/in/jimmy-z-096b031b2/"
              target="_blank"
            >
              <IconLinkedin />
            </a>
            <a href="https://github.com/rocket-fish" target="_blank">
              <IconGithub />
            </a>
          </div> -->
          </div>
        </div>
      </div>
    </div>
  </section>
</template>
<style scoped>
.hero {
  display: flex;
  align-items: center;
  justify-content: center;
  min-height: 99vh;
}

.hero-heading {
  background: var(--gradient-primary-accent-300);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
  text-fill-color: transparent;
}

.hero-description {
  color: var(--c-white);
}

.hero__layout {
  width: 100%;
  display: flex;
  align-items: center;
  justify-content: start;
}

.hero__background {
  position: absolute;
  top: 0;
  bottom: 0;
  right: 0;
  left: 0;

  background: linear-gradient(
    0deg,
    var(--color-background) 0%,
    transparent 10%
  );
}

.hero-card {
  background-color: var(--color-sheer-legibility);
}

.hero-card__cta {
  margin-top: 1rem;
  display: flex;
  justify-content: space-between;
  align-items: center;

  width: 100%;
}

.hero-card__icon-container {
  display: flex;
  gap: 1rem;
}
</style>
