<template>
  <footer>
    <div class="main-footer">
      <img src="@/assets/images/footer/Notus-logo-footer.svg" />
    </div>
    <div class="floating-footer">
      <div class="copyright-notus">
        <p>&#169; {{ new Date().getFullYear() }}. Notus IT d.o.o.</p>
      </div>
    </div>
  </footer>
</template>

<script>
export default {
}
</script>

<style lang="scss">
footer {
  position: relative;

  .main-footer {
    min-height: 12.5rem;
    width: 100%;
    display: flex;
    align-items: center;
    justify-content: center;

    @media screen and (max-width: 767px) {
      min-height: 9.375rem;
    }

    img {
      @media screen and (max-width: 767px) {
        width: 13rem;
      }
    }
  }

  .floating-footer {
    background-color: $secondary-text;
    max-width: 1200px;
    width: 100%;
    min-height: 6.25rem;
    position: absolute;
    top: 0;
    left: 50%;
    transform: translate(-50%, -50%);
    display: flex;
    align-items: center;
    justify-content: center;

    @media screen and (max-width: 768px) {
      position: relative;
      transform: unset;
      left: unset;
      top: unset;
    }

    p {
      color: #fff;
      transform: matrix(1, 0, 0, 1, 0, 0);
    }
  }
}
</style>
