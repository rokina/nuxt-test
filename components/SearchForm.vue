<template>
  <form action="/search/" class="c-form">
    <input
      class="c-form__input"
      placeholder="記事検索"
      type="text"
      name="q"
      size="10"
    />
    <input class="c-form__button" type="submit" value="検索" method="get" />
  </form>
</template>

<script>
export default {}
</script>

<style lang="scss" scoped>
.c-form {
  position: absolute;
  top: -90px;
  right: 30px;
  display: flex;
  &__input {
    font-size: 1.4rem;
    border: 1px solid #ddd;
    padding: 3px 7px;
    border-radius: 4px 0 0 4px;
    transition: 0.3s;
    &:focus {
      outline: none;
      border-color: #444;
    }
  }
  &__button {
    font-size: 1.2rem;
    background: #444;
    padding: 2px 7px;
    color: #fff;
    border-radius: 0 4px 4px 0;
    transition: opacity 0.3s;
    &:hover {
      opacity: 0.7;
    }
  }
}
</style>
