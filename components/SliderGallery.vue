<template>
  <swiper class="swiper gallery-slider-swiper" :options="swiperOption">
    <swiper-slide>
      <img src="@/assets/images/slider/notus-task3-img1.jpg" />
    </swiper-slide>
    <swiper-slide>
      <img src="@/assets/images/slider/notus-task3-img2.jpg" />
    </swiper-slide>
    <swiper-slide>
      <img src="@/assets/images/slider/notus-task3-img3.jpg" />
    </swiper-slide>
    <swiper-slide>
      <img src="@/assets/images/slider/notus-task3-img4.jpg" />
    </swiper-slide>
    <div class="swiper-button-prev" slot="button-prev"></div>
    <div class="swiper-button-next" slot="button-next"></div>
  </swiper>
</template>

<script>
import { Swiper, SwiperSlide } from 'vue-awesome-swiper'

export default {
  components: {
    Swiper,
    SwiperSlide
  },
  data() {
    return {
      swiperOption: {
        slidesPerView: 3,
        spaceBetween: 50,
        loop: true,
        navigation: {
          nextEl: '.swiper-button-next',
          prevEl: '.swiper-button-prev'
        }
      }
    }
  }
}
</script>

<style lang="scss">
.gallery-slider-swiper {
  max-width: 930px;
  width: 100%;
  margin: 0 auto;
  position: unset;

  img {
    min-height: 550px;
  }
}
</style>
