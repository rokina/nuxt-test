<template>
  <ul class="c-pager">
    <li class="c-pager__list">
      <nuxt-link
        :to="{ path: `/` }"
        class="c-pager__item"
        :class="{ 'is-active': pageNum == 1 }"
        >1</nuxt-link
      >
    </li>
    <!-- <li class="c-pager__list">
      <nuxt-link :to="{path: `/page/2`}" class="c-pager__item" :class="{'is-active': pageNum==2}">2</nuxt-link>
    </li> -->
  </ul>
</template>

<script>
export default {
  data() {
    return {
      pageNum: this.$route.params.p || '1'
    }
  }
}
</script>

<style lang="scss" scoped>
.c-pager {
  $root: &;

  text-align: center;
  display: flex;
  justify-content: center;
  &__list {
    list-style: none;
    + #{$root}__list {
      margin-left: 15px;
    }
  }
  &__item {
    width: 50px;
    height: 50px;
    display: flex;
    align-items: center;
    justify-content: center;
    text-decoration: none;
    font-size: 3rem;
    border-radius: 50%;
    transition: background-color 0.3s, color 0.3s;
    &:hover {
      background: #666;
      color: #fff;
    }
    &.is-active {
      background: #333;
      color: #fff;
      pointer-events: none;
    }
  }
}
</style>
