<template>
  <div class="menu-burger-holder">
    <Slide :closeOnNavigation="true">
      <div class="menu-logo-holder">
        <img src="@/assets/images/logo/Notus-logo-meni.svg" />
      </div>
      <div class="menu-items-holder">
        <NuxtLink :to="{ path: '/',hash:'task3'}">
          <span>Task3</span>
        </NuxtLink>
        <NuxtLink :to="{ path: '/',hash:'task4'}">
          <span>Task4</span>
        </NuxtLink>
        <NuxtLink :to="{ path: '/',hash:'task5'}">
          <span>Task5</span>
        </NuxtLink>
      </div>
    </Slide>
  </div>
</template>

<script>
export default {
}
</script>

<style lang="scss">
.menu-burger-holder {
  .bm-menu {
    background-color: $secondary;

    .bm-item-list {
      margin-left: 0;

      .menu-logo-holder {
        align-items: center;
        justify-content: center;
        width: 100%;
      }

      .menu-items-holder {
        margin-left: 13.02vw;
        flex-direction: column;
        margin-top: 16.6vh;

        a {
          color: #fff;
          font-size: 3.75rem;
          font-weight: bold;
          text-transform: uppercase;
          margin-bottom: 1.875rem;
          width: fit-content;
        }
      }
    }

    .cross-style {
      right: unset;
      left: 6.25rem;
      top: 8.125rem;
      display: flex;
      align-items: center;
      justify-content: center;

      .bm-cross {
        background-color: $primary !important;
        width: 1.5px !important;
        height: 18px !important;
      }

      .bm-cross:nth-child(1) {
        transform: rotate(-60deg) !important;
      }

      .bm-cross:nth-child(2) {
        transform: rotate(60deg) !important;
      }
    }
  }

  .bm-burger-button {
    position: fixed;
    z-index: 99;
    top: 8.125rem;
    left: 6.25rem;
    height: 1.1rem;
    width: 1.625rem;
  }

  .bm-burger-bars {
    background-color: $secondary;
  }

  .line-style {
    height: 2px;
  }

  .line-style:nth-child(2) {
    width: 22px;
  }
}
</style>
