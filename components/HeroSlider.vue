<template>
  <div>
    <div class="hero-swiper-overlay" />
    <swiper class="swiper hero-swiper" :options="swiperOption">
      <swiper-slide v-for="(img, index) in heroSwiper" :key="index">
        <img :src="img.heroSwiperImage" />
      </swiper-slide>
      <div class="swiper-button-prev" slot="button-prev"></div>
      <div class="swiper-pagination" slot="pagination"></div>
      <div class="swiper-button-next" slot="button-next"></div>
    </swiper>
  </div>
</template>

<script>
import { Swiper, SwiperSlide } from 'vue-awesome-swiper'

export default {
  components: {
    Swiper,
    SwiperSlide
  },
  props: {
    heroSwiper: {
      type: Array,
      required: true,
    },

    swiperOption: {
      type: Object,
      required: true,
    },
  }
}
</script>

<style lang="scss">
.hero-swiper-overlay {
  position: absolute;
  z-index: 3;
  width: 100%;
  height: 100%;
  pointer-events: none;
  background-color: rgba(8, 27, 47, 0.7);
}

.swiper.hero-swiper {
  height: 100vh;
  position: unset;

  .swiper-slide {
    img {
      width: 100%;
      height: 100%;
      object-fit: cover;
      object-position: center;
    }
  }

  .swiper-pagination {
    bottom: 6.25rem;
    height: 1.875rem;
    display: flex;
    justify-content: center;
    align-items: center;
    font-size: 1rem;
    color: #fff;
    opacity: 0.6;
  }

  .swiper-button-next,
  .swiper-button-prev {
    top: unset;
    bottom: 6.25rem;
  }

  .swiper-button-prev {
    left: 45vw;
  }

  .swiper-button-next {
    right: 45vw;
  }
}
</style>
