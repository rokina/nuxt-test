<template>
  <article class="c-card">
    <a href="#" class="c-card__item">
      <span class="c-card__label">お知らせ</span>
      <img
        src="http://placehold.jp/400x250.png"
        alt=""
        class="c-card__thumbnail"
      />
      <div class="c-card__content">
        <span class="c-card__date">2021.03.01</span>
        <p class="c-card__title">
          サンプルサンプルサンプルサンプルサンプルサンプルサンプルサンプル
        </p>
      </div>
    </a>
  </article>
</template>

<style lang="scss" scoped>
.c-card {
  display: inline-block;
  width: 400px;
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
