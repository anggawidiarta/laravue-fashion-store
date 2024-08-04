<script setup>
import { Carousel, Slide } from 'vue3-carousel'
import 'vue3-carousel/dist/carousel.css'

const logos = [
  '/img/logo-carousel/logo-1.png',
  '/img/logo-carousel/logo-2.png',
  '/img/logo-carousel/logo-3.png',
  '/img/logo-carousel/logo-4.png',
  '/img/logo-carousel/logo-5.png',
  '/img/logo-carousel/logo-1.png',
  '/img/logo-carousel/logo-2.png',
  '/img/logo-carousel/logo-3.png',
  '/img/logo-carousel/logo-4.png',
  '/img/logo-carousel/logo-5.png'
]

const breakpoints = {
  1200: { itemsToShow: 5 },
  992: { itemsToShow: 4 },
  768: { itemsToShow: 3 },
  576: { itemsToShow: 2 },
  0: { itemsToShow: 1 }
}
</script>

<template>
  <div class="partner-logo">
    <div class="container">
      <Carousel
        :breakpoints="breakpoints"
        touch-drag="false"
        mouse-drag="false"
        wrap-around="true"
        autoplay="3000"
        transition="1250"
      >
        <Slide v-for="(logo, index) in logos" :key="index">
          <div class="logo-item">
            <div class="tablecell-inner">
              <img :src="logo" alt="Partner Logo" />
            </div>
          </div>
        </Slide>
      </Carousel>
    </div>
  </div>
</template>
