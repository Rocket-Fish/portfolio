<script setup lang="ts">
import LavaLamp from "./LavaLamp.vue";
</script>
<template>
  <section class="hero">
    <div class="hero__background">
      <LavaLamp />
    </div>
    <div class="hero__layout container">
      <div class="hero-card transparent-card tarnsparent-card--large">
        <p class="body body-m semi-bold hero-description">
          Hi, I'm Jimmy, I am a
        </p>
        <h1 class="hero-heading heading heading--xxl">
          Software Engineer<br />& More
        </h1>
        <p class="body body-m semi-bold hero-description">
          I build intuitive, secure, and performant web applications.
        </p>
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
  background: var(--gradient-primary-accent);
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
  right: -2rem;
  left: -2rem;
}

.hero-card {
  background-color: var(--color-sheer-legibility);
}
</style>
