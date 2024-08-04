<script setup>
import HomeHeader from '@/components/HomeHeader.vue'
import { Carousel, Slide } from 'vue3-carousel'
import { ref } from 'vue'
import HomeFooter from '@/components/HomeFooter.vue'

const images = ['/img/mickey1.jpg', '/img/mickey2.jpg', '/img/mickey3.jpg', '/img/mickey4.jpg']
const selectedImage = ref(images[0]) // Initialize with the first image

// Function to change the selected image
const changeImage = (image) => {
  selectedImage.value = image
}
</script>

<template>
  <div class="product">
    <HomeHeader />
    <!-- #region breadcrumb -->
    <div class="breacrumb-section text-left">
      <div class="container">
        <div class="row">
          <div class="col-lg-12">
            <div class="breadcrumb-text product-more">
              <router-link to="/"> <i class="fa fa-home"></i> Home </router-link>
              <span>Detail</span>
            </div>
          </div>
        </div>
      </div>
    </div>
    <!-- #endregion -->

    <!-- #region product shop -->
    <section class="product-shop spad page-details">
      <div class="container">
        <div class="row">
          <div class="col-lg-12">
            <div class="row">
              <div class="col-lg-6">
                <div class="product-pic-zoom">
                  <img class="product-big-img" :src="selectedImage" alt="" />
                </div>
                <div class="product-thumbs">
                  <Carousel class="product-thumbs-track ps-slider" :items-to-show="4" :loop="true">
                    <Slide
                      v-for="(image, index) in images"
                      :key="index"
                      :index="index"
                      class="mr-2"
                      @click="changeImage(image)"
                    >
                      <div class="pt" :style="{ backgroundImage: `url(${image})` }">
                        <img :src="image" alt="" />
                      </div>
                    </Slide>
                  </Carousel>
                </div>
              </div>
              <div class="col-lg-6">
                <div class="product-details">
                  <div class="pd-title">
                    <span>oranges</span>
                    <h3>Pure Pineapple</h3>
                  </div>
                  <div class="pd-desc">
                    <p>
                      Lorem ipsum dolor sit amet consectetur adipisicing elit. Corporis, error
                      officia. Rem aperiam laborum voluptatum vel, pariatur modi hic provident eum
                      iure natus quos non a sequi, id accusantium! Autem.
                    </p>
                    <p>
                      Lorem ipsum dolor sit, amet consectetur adipisicing elit. Quam possimus
                      quisquam animi, commodi, nihil voluptate nostrum neque architecto illo
                      officiis doloremque et corrupti cupiditate voluptatibus error illum. Commodi
                      expedita animi nulla aspernatur. Id asperiores blanditiis, omnis repudiandae
                      iste inventore cum, quam sint molestiae accusamus voluptates ex tempora illum
                      sit perspiciatis. Nostrum dolor tenetur amet, illo natus magni veniam quia sit
                      nihil dolores. Commodi ratione distinctio harum voluptatum velit facilis
                      voluptas animi non laudantium, id dolorem atque perferendis enim ducimus? A
                      exercitationem recusandae aliquam quod. Itaque inventore obcaecati, unde quam
                      impedit praesentium veritatis quis beatae ea atque perferendis voluptates
                      velit architecto?
                    </p>
                    <h4>$495.00</h4>
                  </div>
                  <div class="quantity">
                    <a href="shopping-cart.html" class="primary-btn pd-cart">Add To Cart</a>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>
    <!-- #endregion -->

    <!-- #region related product -->
    <div class="related-products spad">
      <div class="container">
        <div class="row">
          <div class="col-lg-12">
            <div class="section-title">
              <h2>Related Products</h2>
            </div>
          </div>
        </div>
        <div class="row">
          <div class="col-lg-3 col-sm-6">
            <div class="product-item">
              <div class="pi-pic">
                <img src="/img/products/women-1.jpg" alt="" />
                <ul>
                  <li class="w-icon active">
                    <a href="#"><i class="icon_bag_alt"></i></a>
                  </li>
                  <li class="quick-view"><a href="#">+ Quick View</a></li>
                </ul>
              </div>
              <div class="pi-text">
                <div class="catagory-name">Coat</div>
                <a href="#">
                  <h5>Pure Pineapple</h5>
                </a>
                <div class="product-price">
                  $14.00
                  <span>$35.00</span>
                </div>
              </div>
            </div>
          </div>
          <div class="col-lg-3 col-sm-6">
            <div class="product-item">
              <div class="pi-pic">
                <img src="/img/products/women-2.jpg" alt="" />
                <ul>
                  <li class="w-icon active">
                    <a href="#"><i class="icon_bag_alt"></i></a>
                  </li>
                  <li class="quick-view"><a href="#">+ Quick View</a></li>
                </ul>
              </div>
              <div class="pi-text">
                <div class="catagory-name">Shoes</div>
                <a href="#">
                  <h5>Guangzhou sweater</h5>
                </a>
                <div class="product-price">$13.00</div>
              </div>
            </div>
          </div>
          <div class="col-lg-3 col-sm-6">
            <div class="product-item">
              <div class="pi-pic">
                <img src="/img/products/women-3.jpg" alt="" />
                <ul>
                  <li class="w-icon active">
                    <a href="#"><i class="icon_bag_alt"></i></a>
                  </li>
                  <li class="quick-view"><a href="#">+ Quick View</a></li>
                </ul>
              </div>
              <div class="pi-text">
                <div class="catagory-name">Towel</div>
                <a href="#">
                  <h5>Pure Pineapple</h5>
                </a>
                <div class="product-price">$34.00</div>
              </div>
            </div>
          </div>
          <div class="col-lg-3 col-sm-6">
            <div class="product-item">
              <div class="pi-pic">
                <img src="/img/products/women-4.jpg" alt="" />
                <ul>
                  <li class="w-icon active">
                    <a href="#"><i class="icon_bag_alt"></i></a>
                  </li>
                  <li class="quick-view"><a href="#">+ Quick View</a></li>
                </ul>
              </div>
              <div class="pi-text">
                <div class="catagory-name">Towel</div>
                <a href="#">
                  <h5>Converse Shoes</h5>
                </a>
                <div class="product-price">$34.00</div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
    <!-- #endregion -->

    <HomeFooter />
  </div>
</template>
