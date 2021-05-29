<template>
  <div>
    <swiper class="swiper" :options="swiperOption">
      <swiper-slide v-for="(img, index) in heroSwiper" :key="index">
        <img :src="img.heroSwiperImage" />
      </swiper-slide>
      <div class="swiper-pagination" slot="pagination"></div>
      <div class="swiper-button-prev" slot="button-prev"></div>
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

</style>
