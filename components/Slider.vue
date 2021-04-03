<template>
  <!-- <div class="c-slider">
    <img src="http://placehold.jp/1200x600.png" alt="" />
  </div> -->
  <div class="c-slider">
    <swiper :options="swiperOption">
      <swiper-slide v-for="content in sliderData" :key="content.id">
        <nuxt-link :to="`/${content.id}`" class="c-slider__item">
          <img :src="content.mainVisual.url" alt="" class="" />
          <div class="c-slider__block">
            <p class="c-slider__date">
              {{ $moment(content.publishedAt).format('YYYY.MM.DD') }}
            </p>
            <p class="c-slider__title">{{ content.title }}</p>
          </div>
        </nuxt-link>
      </swiper-slide>
    </swiper>
    <div slot="pagination" class="swiper-pagination" />
  </div>
</template>

<script>
export default {
  data() {
    return {
      swiperOption: {
        autoplay: {
          delay: 2500,
          disableOnInteraction: true
        },
        pagination: {
          //ページネーション設定
          el: '.swiper-pagination',
          clickable: true
        },
        speed: 1000,
        slidesPerView: 1,
        loop: true,
        spaceBetween: 0
      }
    }
  },
  props: ['sliderData']
}
</script>

<style lang="scss">
.c-slider {
  width: 1200px;
  margin: auto;
  position: relative;
  &__item {
    display: block;
    transition: opacity 0.3s;
    &:hover {
      opacity: 0.7;
    }
  }
  &__block {
    position: absolute;
    bottom: 0;
    left: 0;
    right: 0;
    margin: auto;
    padding: 30px 30px 20px;
    text-align: left;
    width: 100%;
    background: linear-gradient(
      to bottom,
      rgba(255, 255, 255, 0) 2%,
      #000 100%
    );
    color: #fff;
    box-sizing: border-box;
  }
  &__title {
    font-size: 2.4rem;
  }
  &__date {
    font-weight: normal;
    font-size: 1.4rem;
    color: #ddd;
  }
}
</style>
<style lang="scss" scoped>
.swiper {
  &-container {
    border: 1px solid #ddd;
    text-align: center;
    width: 1200px;
    height: 675px;
    overflow: hidden;
    background: #fff;
  }
  &-slide {
    position: relative;
    img {
      width: 1200px;
      height: 675px;
      object-fit: cover;
    }
  }
  &-pagination {
    left: 0;
    right: 0;
    bottom: -30px;
    display: flex;
    justify-content: space-between;
    width: 60px;
    margin: auto;
    &-bullet {
      width: 10px;
      height: 10px;
    }
  }
}
</style>
