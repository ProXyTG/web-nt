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
      <div class="gallery-holder">
        <Gallery />
      </div>
      <div class="google-maps-wrapper">
        <GoogleMaps />
      </div>
      <div class="task-5-container">
        <div class="task-5-content">
          <h1>Task 5</h1>
          <div class="task-5-desc">
            <p>Quas enim kakaw Graeci appellant, vitia malo quam malitias nominare. Idem adhuc; Idemque diviserunt naturam hominis in animum et corpus. Istam voluptatem, inquit, Epicurus ignorat? Duo enim genera quae erant, fecit tria.</p>
            <p class="colored">Ut proverbia non nulla veriora sint quam vestra dogmata</p>
            <p>An haec ab eo non dicuntur? Idcirco enim non desideraret, quia, quod dolore caret, id in voluptate est. Quoniam, si dis placet, ab Epicuro loqui discimus. Quid sequatur, quid repugnet, vident.</p>
            <div class="btn-holder">
              <button class="button-anim">
                <span>Hover to have solid fill</span>
              </button>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Loading from '@/components/Loading.vue'
import HeroSlider from '@/components/HeroSlider.vue'
import GoogleMaps from '@/components/GoogleMaps.vue'
import Gallery from '@/components/Gallery.vue'

export default {
  components: {
    Loading,
    HeroSlider,
    GoogleMaps,
    Gallery
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
      ],
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
    position: relative;

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

  .google-maps-wrapper {
    .GMap {
      .GMap__Wrapper {
        height: auto;
        min-height: 37.5rem;
      }
    }
  }

  .task-5-container {
    background-color: #fff;
    padding: 12.5rem 0;

    .task-5-content {
      max-width: 60rem;
      width: 100%;
      margin: 0 auto;
      text-align: center;

      h1 {
        font-weight: 700;
        color: $primary;
        margin-bottom: 6.25rem;
      }

      p {
        color: $primary;
        font-weight: 400;
      }

      p.colored {
        color: $secondary-text;
        font-weight: bold;
        margin-top: 2rem;
      }

      .btn-holder {
        margin: 6.25rem 0 9.688rem 0;

        button:hover, button:focus {
          box-shadow: none;
        }

        button{
          display: inline-block;
          position: relative;
          background: none;
          border: none;
          color: #000;
          font-size: 18px;
          cursor: pointer;
          background: #fff;
        }
        span{
          display: block;
          padding: 1.8rem 2rem;
          font-weight: 700;
        }
        button::before, button::after{
          content:"";
          width: 0;
          height: 4px;
          position: absolute;
          transition: all 0.2s linear;
          background: $secondary;
        }

        span::before, span::after{
          content:"";
          width:4px;
          height:0;
          position: absolute;
          transition: all 0.2s linear;
          background: $secondary;
        }
        button:hover::before, button:hover::after{
          width: 100%;
        }
        button:hover span::before, button:hover span::after{
          height: 100%;
        }

        .button-anim::after{
          left: 0;
          bottom: 0;
          transition-delay: 0.6s;
        }
        .button-anim span::after{
          transition-delay: 0.4s;
          right: 0;
          bottom: 0
        }
        .button-anim::before{
          right: 0;
          top: 0;
          transition-delay: 0.2s;
        }
        .button-anim span::before{
          transition-delay: 0s;
          left: 0;
          top: 0;
        }

        .button-anim:hover::after{
          transition-delay: 0s;
        }
        .button-anim:hover span::after{
          transition-delay: 0.2s;
        }
        .button-anim:hover::before{
          transition-delay: 0.4s;
        }
        .button-anim:hover span::before{
          transition-delay: 0.6s;
        }
      }
    }
  }
}
</style>
