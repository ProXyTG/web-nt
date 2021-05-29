<template>
  <div>
      <div v-if="loading">
        <Loading/>
      </div>
      <div v-else>
        <div>
          asd132
        </div>
      </div>
  </div>
</template>

<script>
import Loading from '@/components/Loading.vue'

export default {
  components: {
    Loading
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

</style>
