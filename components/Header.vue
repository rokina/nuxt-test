<template>
  <header class="c-header" :class="{ 'is-fixed': scrollY > 1 }">
    <h1 class="c-header__logo">
      <a href="/"><img src="@/assets/img/logo.png" alt="" /></a>
    </h1>
    <nav class="c-header__nav">
      <ul class="c-header__lists">
        <li class="c-header__list">
          <nuxt-link to="/categories/uw-3o99hi" class="c-header__item"
            >休暇情報</nuxt-link
          >
        </li>
        <li class="c-header__list">
          <nuxt-link to="/categories/280sbixzvibo" class="c-header__item"
            >日常</nuxt-link
          >
        </li>
        <li class="c-header__list">
          <nuxt-link to="/categories/asjqwlyofn0k" class="c-header__item"
            >エンタメ</nuxt-link
          >
        </li>
      </ul>
    </nav>
  </header>
</template>

<script>
export default {
  data() {
    return {
      scrollY: 0
    }
  },
  mounted() {
    window.addEventListener('scroll', this.handleScroll)
  },
  methods: {
    handleScroll() {
      this.scrollY = window.scrollY
    }
  }
}
</script>

<style lang="scss" scoped>
.c-header {
  padding: 40px 0;
  position: fixed;
  width: 100%;
  background: #fff;
  top: 0;
  z-index: 100;
  transition: 0.4s;
  $root: &;
  &__logo {
    text-align: center;
    a {
      transition: opacity 0.3s;
      display: inline-block;
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
    transition: opacity 0.3s;
    &:hover {
      opacity: 0.7;
    }
  }
  &.is-fixed {
    display: flex;
    padding: 20px 40px;
    #{$root}__logo {
      img {
        width: 150px;
      }
    }
    #{$root}__nav {
      margin-top: 0;
    }
    #{$root}__lists {
      align-items: center;
      height: 100%;
    }
  }
}
</style>
