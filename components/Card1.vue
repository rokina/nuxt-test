<template>
  <div>
    <article class="c-card" v-for="content in pickupData" :key="content.id">
      <nuxt-link :to="`/${content.id}`" class="c-card__item">
        <span class="c-card__label">{{
          content.category && content.category.name
        }}</span>
        <img
          v-if="content.mainVisual"
          :src="content.mainVisual.url"
          alt=""
          class="c-card__thumbnail"
        />
        <img
          v-else
          src="https://images.microcms-assets.io/assets/49f98e2075bc4b10af6d727b1efa9c2b/cca3e5b7438c4f2bbebb56fe2ccd6444/42589447.webp"
          alt=""
          class="c-card__thumbnail"
        />
        <div class="c-card__content">
          <time
            class="c-card__date"
            :datetime="$moment(content.publishedAt).format('YYYY-MM-DD')"
            >{{ $moment(content.publishedAt).format('YYYY.MM.DD') }}</time
          >
          <p class="c-card__title">
            {{ content.title }}
          </p>
        </div>
      </nuxt-link>
    </article>
  </div>
</template>

<script>
export default {
  props: ['pickupData']
}
</script>

<style lang="scss" scoped>
.c-card {
  display: inline-block;
  width: 280px;
  & + & {
    margin-left: 26px;
  }
  &__item {
    display: inherit;
    text-decoration: none;
    transition: opacity 0.3s;
    color: #333;
    position: relative;
    &:hover {
      opacity: 0.7;
    }
  }
  &__label {
    position: absolute;
    top: 0;
    color: #fff;
    font-size: 1.2rem;
    background: #000;
    display: inline-block;
    padding: 2px 10px;
  }
  &__thumbnail {
    display: block;
    width: 280px;
    height: 160px;
    object-fit: cover;
  }
  &__content {
    padding: 10px 15px 15px;
    background: #fff;
  }
  &__date {
    font-size: 1.4rem;
    color: #666;
  }
  &__title {
    margin-top: 5px;
    font-size: 1.8rem;
    line-height: 1.2;
  }
}
</style>
