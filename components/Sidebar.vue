<template>
  <div class="c-sidebar">
    <h2 class="c-sidebar__title">Recommend</h2>
    <ul class="c-lists">
      <li class="c-list">
        <a href="" class="c-list__item">
          <img
            src="http://placehold.jp/80x60.png"
            alt=""
            class="c-list__image"
          />
          <p class="c-list__title">サンプルサンプル</p>
        </a>
      </li>
      <li class="c-list">
        <a href="" class="c-list__item">
          <img
            src="http://placehold.jp/80x60.png"
            alt=""
            class="c-list__image"
          />
          <p class="c-list__title">サンプルサンプル</p>
        </a>
      </li>
      <li class="c-list">
        <a href="" class="c-list__item">
          <img
            src="http://placehold.jp/80x60.png"
            alt=""
            class="c-list__image"
          />
          <p class="c-list__title">サンプルサンプル</p>
        </a>
      </li>
    </ul>
  </div>
</template>

<style lang="scss" scoped>
.c-sidebar {
  width: 270px;
  margin-left: 30px;
  &__title {
    padding: 20px 0;
    border-top: 2px solid #333;
    border-bottom: 2px solid #333;
    text-align: center;
  }
}
.c-list {
  list-style: none;
  &__item {
    padding: 20px 0;
    text-decoration: none;
    display: flex;
    align-items: center;
    border-bottom: 1px solid #ccc;
    transition: opacity 0.3s;
    &:hover {
      opacity: 0.7;
    }
  }
  &__title {
    margin-left: 10px;
    font-size: 1.4rem;
  }
}
</style>
