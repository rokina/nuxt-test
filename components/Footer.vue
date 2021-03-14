<template>
  <footer class="c-footer">
    <nav>
      <ul class="c-nav">
        <li class="c-nav__list">
          <a href="#" class="c-nav__item">会社概要</a>
        </li>
        <li class="c-nav__list">
          <a href="#" class="c-nav__item">利用規約</a>
        </li>
        <li class="c-nav__list">
          <a href="#" class="c-nav__item">プライバシーポリシー</a>
        </li>
      </ul>
    </nav>
    <p class="c-copy">
      <small>&copy; Nuxt,inc.</small>
    </p>
  </footer>
</template>

<style lang="scss" scoped>
.c-footer {
  padding: 80px 0 20px;
  background: #333;
}
.c-nav {
  $root: &;

  width: 1200px;
  margin: auto;
  display: flex;
  flex-wrap: wrap;
  &__list {
    list-style: none;
    & + #{$root}__list {
      margin-left: 20px;
    }
  }
  &__item {
    color: #fff;
    text-decoration: none;
    transition: opacity 0.3s;
    &:hover {
      opacity: 0.7;
    }
  }
}
.c-copy {
  margin-top: 60px;
  color: #fff;
  text-align: center;
  font-size: 1.6rem;
  small {
    font-size: inherit;
  }
}
</style>
