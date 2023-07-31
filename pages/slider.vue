<template>
  <div class="carousel-wrapper">
    <div v-swiper:mySwiper="options">
      <div class="swiper-wrapper">
        <div v-for="i in 5" :key="i" class="img-warpper swiper-slide">
          <img :src="`https://picsum.photos/200/100?random=${i}`" />
        </div>
      </div>
      <div class="swiper-pagination swiper-pagination-bullets"></div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      options: {
        slidesPerView: 3,
        loop: true,
        pagination: {
          el: '.swiper-pagination'
        }
      }
    }
  }
}
</script>

<style lang="scss" scoped>
.carousel-wrapper {
  padding: 40px;
  height: 300px;
  width: 100%;
  .swiper-slide {
    text-align: center;
    display: flex;
    justify-content: center;
    align-items: center;
  }
  .img-warpper img {
    margin: auto;
    width: 200px;
    height: 100px;
    background-image: linear-gradient(gray 100%, transparent 0);
  }
  ::v-deep.swiper-pagination-bullet-active {
    background-color: black;
  }
}
</style>
