<template>
  <header class="c-header">
    <h1 class="c-header__logo"><a href="/"><img src="@/assets/img/logo.png" alt=""></a></h1>
    <nav class="c-header__nav">
      <ul class="c-header__lists">
        <li class="c-header__list"><a href="#" class="c-header__item">新着記事</a></li>
        <li class="c-header__list"><a href="#" class="c-header__item">お知らせ</a></li>
        <li class="c-header__list"><a href="#" class="c-header__item">ブログ</a></li>
      </ul>
    </nav>
  </header>
</template>

<style lang="scss" scoped>
  .c-header {
    padding: 40px 0;
    &__logo {
      text-align: center;
      a {
        transition: opacity .3s;
        &:hover {
          opacity: 0.7;
        }
      }
    }
    &__nav {
      width: 960px;
      margin: 25px auto 0;
    }
    &__lists {
      display: flex;
      justify-content: space-around;
    }
    &__list {
      list-style: none;
    }
    &__item {
      padding: 10px 15px;
      text-decoration: none;
      color: #333;
      transition: opacity .3s;
      &:hover {
        opacity: .7;
      }
    }
  }
</style>
