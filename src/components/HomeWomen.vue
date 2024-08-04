<script setup>
import { Carousel, Slide } from 'vue3-carousel'
import 'vue3-carousel/dist/carousel.css'

const products = [
  {
    image: '/img/mickey1.jpg',
    category: 'Coat',
    title: 'Mickey Baggy',
    price: '$14.00',
    originalPrice: '$35.00',
    quickViewLink: 'product.html'
  },
  {
    image: '/img/products/women-2.jpg',
    category: 'Shoes',
    title: 'Guangzhou sweater',
    price: '$13.00',
    originalPrice: null,
    quickViewLink: '#'
  },
  {
    image: '/img/products/women-3.jpg',
    category: 'Towel',
    title: 'Pure Pineapple',
    price: '$34.00',
    originalPrice: null,
    quickViewLink: '#'
  },
  {
    image: '/img/products/women-4.jpg',
    category: 'Towel',
    title: 'Converse Shoes',
    price: '$34.00',
    originalPrice: null,
    quickViewLink: '#'
  }
]

const breakpoints = {
  1200: { itemsToShow: 3 },
  992: { itemsToShow: 2.5 },
  768: { itemsToShow: 2 },
  576: { itemsToShow: 1.5 },
  0: { itemsToShow: 1 }
}
</script>

<template>
  <section class="women-banner spad mt-6">
    <div class="container-fluid">
      <div class="row">
        <div class="col-lg-12 mt-5">
          <Carousel :breakpoints="breakpoints" wrap-around="true">
            <Slide v-for="(item, index) in products" :key="index">
              <div class="product-item object-cover w-full">
                <div class="pi-pic">
                  <img :src="item.image" alt="women image" />
                  <ul>
                    <li class="w-icon active">
                      <a href="#"><i class="icon_bag_alt"></i></a>
                    </li>
                    <li class="quick-view">
                      <a :href="item.quickViewLink">+ Quick View</a>
                    </li>
                  </ul>
                </div>
                <div class="pi-text">
                  <div class="catagory-name">{{ item.category }}</div>
                  <a href="#">
                    <h5>{{ item.title }}</h5>
                  </a>
                  <div class="product-price">
                    {{ item.price }}
                    <span v-if="item.originalPrice">{{ item.originalPrice }}</span>
                  </div>
                </div>
              </div>
            </Slide>
          </Carousel>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.product-item {
  margin-right: 24px;
  /* max-height: 475px; */
}
</style>
