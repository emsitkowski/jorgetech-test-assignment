<script setup lang="ts">
import Header from "./components/Header.vue";
import Card from "./components/Card.vue";
import Button from "./components/Button.vue";

const cards = [
  {
    title: "Photography",
    bullets: ["Drone Photography", "Interiors", "Exteriors / Architectural"],
    description: "Every photograph we produce finds the beauty in your property while serving as a profitable asset.",
    image: "/img/card-image-1.jpg",
  },
  {
    title: "Virtual Staging",
    description:
      "Our staging will help you sell the potential of your space. We can work off of our own photography or photos you provide.",
    image: "/img/card-image-2.jpg",
  },
  {
    title: "Renderings",
    bullets: ["Interiors", "Exteriors"],
    description: "Renderings are the gold standard in pre-construction marketing.",
    image: "/img/card-image-3.jpg",
  },
  {
    title: "Interactive Tours",
    bullets: ["Matterport", "Video Walkthroughs"],
    description: "Give your audience the ability to explore your property without requiring in-person travel.",
    image: "/img/card-image-4.jpg",
  },
  {
    title: "Floor Plans",
    bullets: ["On-site Measure", "2D Floor Plans", "3D Floor Plans"],
    description: "We produce laser-precise floor plans faster than any other service.",
    image: "/img/card-image-5.jpg",
  },
  {
    title: "Video",
    bullets: ["Drone Photography", "Interiors", "Exteriors / Architectural"],
    description: "Video content has higher engagement and will help your property stand out online.",
    image: "/img/card-image-6.jpg",
  },
];
</script>

<template>
  <div class="container">
    <!-- Header -->
    <Header />

    <!-- Cards -->
    <div class="cards">
      <Card v-for="card in cards" :key="card.title">
        <!-- Image -->
        <template #image>
          <img :src="card.image" alt="" />
        </template>

        <!-- Title -->
        <template #title>{{ card.title }}</template>

        <!-- Bullet points -->
        <div v-if="card.bullets">
          <ul>
            <li v-for="bullet in card.bullets" :key="bullet">{{ bullet }}</li>
          </ul>
        </div>

        <!-- Description / paragraph -->
        <p>{{ card.description }}</p>
      </Card>
    </div>

    <!-- Call to Action -->
    <div class="get-started">
      <a href="#">
        <Button label="Get Started" />
      </a>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.container {
  max-width: 1320px;
  margin: 0 auto;
  padding: 80px 4%;
  @media (min-width: 1200px) {
    padding: 108px 6%;
  }
}

.cards {
  display: grid;
  grid-template-columns: 1fr;
  gap: 40px 30px;
  @media (min-width: 420px) {
    grid-template-columns: repeat(2, 1fr);
  }
  @media (min-width: 1200px) {
    grid-template-columns: repeat(3, 1fr);
  }

  & ul {
    list-style-position: inside;

    > li {
      font-weight: 700;
      line-height: 26px;

      &::marker {
        color: #d2ad81;
      }
    }
  }
}

.get-started {
  display: flex;
  justify-content: center;
  margin-top: 80px;
}
</style>
