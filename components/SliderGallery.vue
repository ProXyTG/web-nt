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
        navigation: {
          nextEl: '.swiper-button-next',
          prevEl: '.swiper-button-prev'
        },

        breakpoints: {
          1024: {
            slidesPerView: 3,
            spaceBetween: 50,
          },

          768: {
            slidesPerView: 2,
            spaceBetween: 30,
          },

          300: {
            slidesPerView: 2,
            spaceBetween: 15
          }
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

  @media screen and (min-width: 1023px) and (max-width: 1279px) {
    max-width: 850px;
  }

  @media screen and (min-width: 768px) and (max-width: 1022px) {
    max-width: 620px;
  }

  @media screen and (max-width: 767px) {
    max-width: 300px;
  }

  img {
    min-height: 550px;

    @media screen and (max-width: 767px) {
      min-height: unset;
    }
  }

  .swiper-button-prev {
    @media screen and (max-width: 1279px) {
      left: 0px;
    }
  }

  .swiper-button-next {
    @media screen and (max-width: 1279px) {
      right: 0px;
    }
  }
}
</style>
