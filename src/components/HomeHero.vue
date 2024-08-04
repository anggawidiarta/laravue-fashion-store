<script setup>
import { Carousel, Slide, Navigation, Pagination } from 'vue3-carousel'
import 'vue3-carousel/dist/carousel.css'

const heroItems = [
  {
    image: '/img/hero-1.jpg',
    category: 'Bag, kids',
    title: 'Black friday',
    description:
      'Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore'
  },
  {
    image: '/img/hero-2.jpg',
    category: 'Bag, men, kids',
    title: 'Black friday',
    description:
      'Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore'
  },
  {
    image: '/img/hero-3.jpg',
    category: 'Bag, women, kids',
    title: 'Black friday',
    description:
      'Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore'
  }
]
</script>

<template>
  <!-- Hero Section Begin -->
  <section class="hero-section">
    <Carousel
      class="hero-items"
      :items-to-show="1"
      wrap-around="true"
      autoplay="3000"
      transition="1250"
    >
      <slide v-for="(item, index) in heroItems" :key="index">
        <div
          class="single-hero-items set-bg w-full max-md:!pt-12"
          :style="{ backgroundImage: `url(${item.image})` }"
        >
          <div class="container">
            <div class="row">
              <div class="col-lg-5">
                <span class="" style="opacity: 1">{{ item.category }}</span>
                <h1>{{ item.title }}</h1>
                <p>{{ item.description }}</p>
                <a href="#" class="primary-btn hidden md:block">Shop Now</a>
              </div>
            </div>
          </div>
        </div>
      </slide>
      <template #addons>
        <Navigation />
        <Pagination />
      </template>
    </Carousel>
  </section>
  <!-- Hero Section End -->
</template>

<style scoped></style>
