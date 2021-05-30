<template>
  <div>
    <div class="loading-page" :class="{ 'is-loaded': !loading }">
      <Loading/>
    </div>
    <Nuxt />
    <Footer />
  </div>
</template>

<script>
import Footer from '@/components/Footer.vue'

export default {
  components: {
    Footer
  },
  data() {
    return {
      loading: true
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
</style>
