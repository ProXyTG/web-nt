<template>
  <div class="loading-section">
    <div class="loading-container">
      <div class="loading-logo-holder">
        <img src="@/assets/images/logo/Notus-logo-loading.svg" />
      </div>
    </div>
  </div>
</template>

<script>
export default {

}
</script>

<style lang="scss">
.loading-section {
  .loading-container {
    position: absolute;
    width: 100%;
    height: 100%;
    background-color: $primary;

    .loading-logo-holder {
      display: flex;
      align-items: center;
      justify-content: center;
      height: 100%;

      img {
        transform: scale(1);
        opacity: 1;
	      animation: loading-pulse-effect 3s infinite;
      }
    }
  }
}
</style>
