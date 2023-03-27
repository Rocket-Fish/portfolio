<script setup lang="ts">
// gotta give credit where credit is due
// this component has been adapted from this person's code pen https://codepen.io/mosfetti/pen/JjaYaVy
import { ref, reactive, onMounted, onUnmounted, computed } from "vue";

type Circle = {
  x: number;
  y: number;
  xSpeed: number;
  ySpeed: number;
  radius: number;
};

type Bounds = {
  minX: number;
  minY: number;
  maxX: number;
  maxY: number;
};

const windowResizeCounter = ref(0);

const circles = ref<Circle[]>([]);
const bounds = computed<Bounds>(() => {
  let maxX = 450;
  let maxY = 800;
  let minX = -150;

  windowResizeCounter.value;

  if (lavaLampElement.value) {
    maxX = lavaLampElement.value.clientWidth + 100;
    maxY = lavaLampElement.value.clientHeight + 100;

    if (lavaLampElement.value.clientWidth >= 768) {
      minX = Math.floor(lavaLampElement.value.clientWidth / 2) - 150;
    }
  }

  return {
    minX,
    minY: -150,
    maxX,
    maxY,
  };
});

const updateCirclePosition = (c: Circle) => {
  const circle: Circle = {
    x: c.x + c.xSpeed,
    y: c.y + c.ySpeed,
    xSpeed: c.xSpeed,
    ySpeed: c.ySpeed,
    radius: c.radius,
  };
  if (circle.x < bounds.value.minX) {
    circle.x = bounds.value.minX + Math.random();
    circle.xSpeed = Math.abs(circle.xSpeed);
  } else if (circle.x > bounds.value.maxX) {
    circle.x = bounds.value.maxX - Math.random() * 10;
    circle.xSpeed = -Math.abs(circle.xSpeed);
  }
  if (circle.y < bounds.value.minY) {
    circle.y = bounds.value.minY + Math.random() * 10;
    circle.ySpeed = Math.abs(circle.ySpeed);
  } else if (circle.y > bounds.value.maxY) {
    circle.y = bounds.value.maxY - Math.random() * 10;
    circle.ySpeed = -Math.abs(circle.ySpeed);
  }
  return circle;
};

let interval: number | null = null;
const lavaLampElement = ref<SVGElement | null>(null);

const onWindowResize = () => {
  windowResizeCounter.value += 1;
};

onMounted(() => {
  const defaultCircles = [
    { x: 500, y: 200, xSpeed: 0.2, ySpeed: 0.34, radius: 170 },
    { x: 200, y: 400, xSpeed: 0.5, ySpeed: 0.5, radius: 90 },
    { x: 300, y: 600, xSpeed: 0.3, ySpeed: -0.6, radius: 120 },
    { x: 400, y: 500, xSpeed: -0.1, ySpeed: 0.6, radius: 140 },
    { x: 500, y: 300, xSpeed: 0.2, ySpeed: 0.3, radius: 70 },
  ];

  try {
    if (lavaLampElement.value) {
      // spawn number of circles proportional to width, concentrate them towards 60% to the right side of the screen
      const elementWidth = lavaLampElement.value.clientWidth;
      const elementHeight = lavaLampElement.value.clientHeight;
      const numberOfCircles = Math.ceil(elementWidth / 200);

      const getRandom = (min: number, max: number) => {
        return Math.random() * (max - min) + min;
      };

      const randomPositivity = (biasTowardsPositive = 0.5) => {
        // bias must be between 0 and 1 otherwise it'll always be true;
        return Math.random() < biasTowardsPositive ? 1 : -1;
      };

      for (let i = 0; i < numberOfCircles; i++) {
        circles.value.push({
          x: Math.floor(getRandom(elementWidth * 0.5, elementWidth * 0.8)),
          y: Math.floor(getRandom(elementHeight * 0.2, elementHeight * 0.8)),
          xSpeed: getRandom(0.1, 0.2) * randomPositivity(),
          ySpeed: getRandom(0.1, 0.6) * randomPositivity(0.69),
          radius: Math.floor(getRandom(90, 169)),
        });
      }
    } else {
      throw Error("element not found");
    }
  } catch (e) {
    circles.value = defaultCircles;
  }
  window.addEventListener("resize", onWindowResize);
  interval = setInterval(() => {
    circles.value = circles.value.map((circle) => updateCirclePosition(circle));
  }, 10);
});

onUnmounted(() => {
  window.removeEventListener("resize", onWindowResize);
  if (interval) clearInterval(interval);
});
</script>
<template>
  <svg class="lavalamp" ref="lavaLampElement">
    <defs>
      <filter id="gooify" width="400%" x="-10%" height="400%" y="-150%">
        <feGaussianBlur in="SourceGraphic" stdDeviation="15" result="blur" />
        <feColorMatrix
          in="blur"
          mode="matrix"
          values="1 0 0 0 0
                  0 1 0 0 0
                  0 0 1 0 0
                  0 0 0 25 -10"
        />
      </filter>

      <linearGradient id="lavaGradient" x1="0%" y1="0%" x2="0%" y2="100%">
        <stop offset="0%" stop-color="#05668d" />
        <stop offset="100%" stop-color="#11279a" />
      </linearGradient>
    </defs>

    <g filter="url(#gooify)">
      <circle
        v-for="(circle, index) in circles"
        :key="`circle${index}`"
        class="blobb blur"
        fill="url(#lavaGradient)"
        :cx="circle.x"
        :cy="circle.y"
        :r="circle.radius"
      />
    </g>
  </svg>
</template>
<style scoped>
.blobb {
  fill: url(#lavaGradient);
}

.blur {
  filter: blur(64px);
}

.lavalamp {
  z-index: -100;
  width: 100%;
  height: 100%;
  overflow: hidden;
}
</style>
