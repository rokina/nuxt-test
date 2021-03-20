<template>
  <!-- <div class="c-slider">
    <img src="http://placehold.jp/1200x600.png" alt="" />
  </div> -->
  <div>
    <swiper>
      <swiper-slide
        :options="swiperOption"
        v-for="content in sliderData"
        :key="content.id"
      >
        <img
          v-if="content.mainVisual"
          :src="content.mainVisual.url"
          alt=""
          class=""
        />
        <img
          v-else
          src="https://images.microcms-assets.io/assets/49f98e2075bc4b10af6d727b1efa9c2b/f841755072434234bf36da1cc8a90b77/42589447.jpg"
          alt=""
          class=""
        />
      </swiper-slide>
    </swiper>
  </div>
</template>

<style lang="scss" scoped>
.c-slider {
  width: 1200px;
  margin: auto;
}
.swiper-container {
  text-align: center;
}
.swiper-slide img {
  width: 1200px;
  height: 600px;
  object-fit: cover;
}
</style>

<script>
export default {
  data() {
    return {
      swiperOption: {
        autoplay: {
          delay: 2500,
          disableOnInteraction: false
        },
        slidesPerView: 1,
        loop: true
      }
    }
  },
  props: ['sliderData']
}
</script>
