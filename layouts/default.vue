<template>
  <div>
    <div class="loading-page" :class="{ 'is-loaded': !loading }">
      <Loading/>
    </div>
    <Header />
    <Nuxt />
    <Footer />
  </div>
</template>

<script>
import Footer from '@/components/Footer.vue'
import Header from '@/components/Header.vue'

export default {
  components: {
    Footer,
    Header
  },
  data() {
    return {
      loading: true
    }
  },

  mounted() {
    this.$nextTick(() => {
      document.getElementsByTagName('html')[0].style.overflow = 'hidden'
      setTimeout(() =>
        this.loadingFunc(), 5000)
    })
  },
  methods: {
    loadingFunc() {
      this.loading = false,
      document.getElementsByTagName('html')[0].style.overflow = 'auto'
    }
  }
}
</script>

<style lang="scss">
.loading-page {
  pointer-events: none;
  opacity: 1;
  z-index: 999;
  width: 100%;
  height: 100%;
  position: absolute;
  transition: all .8s ease-in-out;
}

.loading-page.is-loaded {
  opacity: 0;
}

.scroll-restrictions {
  overflow: hidden;
}
</style>
