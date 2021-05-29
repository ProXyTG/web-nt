<template>
  <div>
      <div v-if="loading">
        <Loading/>
      </div>
      <div v-else>
        <HeroSlider
          :swiperOption="heroSwiperOption"
          :heroSwiper="heroImages"
        />
      </div>
  </div>
</template>

<script>
import Loading from '@/components/Loading.vue'
import HeroSlider from '@/components/HeroSlider.vue'

export default {
  components: {
    Loading,
    HeroSlider
  },

  data() {
    return {
      loading: true,
      heroSwiperOption: {
        pagination: {
          el: '.swiper-pagination',
          type: 'fraction'
        },
        navigation: {
          nextEl: '.swiper-button-next',
          prevEl: '.swiper-button-prev'
        }
      },
      heroImages: [
        {
          heroSwiperImage: require('~/assets/images/hero/hero-image-1.jpg')
        },
        {
          heroSwiperImage: require('~/assets/images/hero/hero-image-2.jpg')
        },
        {
          heroSwiperImage: require('~/assets/images/hero/hero-image-3.jpg')
        }
      ]
    }
  },

  mounted() {
    this.$nextTick(() => {
      setTimeout(() => this.loading = false, 5000)
    })
  }
}
</script>

<style lang="scss">

</style>
