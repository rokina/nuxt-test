<template>
  <div class="c-conts">
    <Card2 :postsData="postsData"></Card2>
  </div>
</template>

<script>
export default {
  props: ['postsData']
}
</script>

<style lang="scss" scoped>
.c-conts div {
  width: 830px;
  display: flex;
  justify-content: space-between;
  flex-wrap: wrap;
}
</style>
