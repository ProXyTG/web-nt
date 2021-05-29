<template>
  <div>
    <div v-if="loading">
      <Loading/>
    </div>
    <div v-else class="landing-page-container">
      <div class="landing-hero-swiper">
        <div class="logo-holder">
          <img src="@/assets/images/logo/Notus-logo-main.svg" />
        </div>
        <div class="landing-hero-container">
          <div class="landing-hero-content">
            <h1>Notus Front-end test</h1>
          </div>
        </div>
        <HeroSlider
          :swiperOption="heroSwiperOption"
          :heroSwiper="heroImages"
        />
      </div>
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
.landing-page-container {
  position: relative;

  .landing-hero-swiper {
    height: 100vh;

    .logo-holder {
      position: absolute;
      z-index: 9;
      display: flex;
      justify-content: center;
      width: 100%;
      top: 6.25rem;
    }

    .landing-hero-container {
      position: absolute;
      z-index: 9;
      width: 100%;
      height: 100%;

      .landing-hero-content {
        height: 100%;
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;

        h1 {
          color: #fff;
          font-weight: 700;
        }
      }
    }
  }
}
</style>
