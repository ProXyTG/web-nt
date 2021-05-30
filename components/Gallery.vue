<template>
  <div class="gallery-content">
    <div class="gallery-text">
      <h1>
        Task 3
      </h1>
      <p>
        Lorem ipsum dolor sit amet, consectetur adipiscing elit. Duo Reges: constructio interrete.
        Ut aliquid scire se gaudeant? Illi enim inter se dissentiunt. Nec vero sum nescius esse
        utilitatem in historia, non modo voluptatem. Quamquam te quidem video minime esse
        deterritum.
      </p>
    </div>
    <div class="gallery-container">
      <div class="first-column">
        <img src="@/assets/images/gallery/notus-task2-img4.jpg" />
      </div>
      <div class="second-column-up">
        <img src="@/assets/images/gallery/notus-task2-img1.jpg" />
      </div>
      <div class="second-column-down">
        <img src="@/assets/images/gallery/notus-task2-img3.jpg" />
      </div>
      <div class="third-column">
        <img src="@/assets/images/gallery/notus-task2-img2.jpg" />
      </div>
    </div>
  </div>
</template>

<script>
export default {
}
</script>

<style lang="scss">
.gallery-content {
  background-color: #fff;
  padding: 9.375rem 3%;

  .gallery-text {
    text-align: center;
    max-width: 60rem;
    width: 100%;
    margin: 0 auto;

    h1 {
      color: $primary;
      font-weight: 700;
      margin-bottom: 3.125rem;
    }

    p {
      color: $primary-text;
      font-weight: 400;
      margin-bottom: 6.25rem;
    }
  }

  .gallery-container {
    max-width: 1230px;
    width: 100%;
    margin: 0 auto;
    display: grid;
    grid-template-columns: 1fr 1fr 1fr 1fr;
    grid-template-rows: 1fr 1fr 1fr 1fr;
    gap: 30px 30px;
    place-items: center;
    grid-template-areas:
      "first-column second-column-up second-column-up third-column"
      "first-column second-column-up second-column-up third-column"
      "first-column second-column-down second-column-down third-column"
      "first-column second-column-down second-column-down third-column";
  }

  .first-column { grid-area: first-column; }
  .second-column-up { grid-area: second-column-up; }
  .second-column-down { grid-area: second-column-down; }
  .third-column { grid-area: third-column; }
}
</style>
