<template>
  <section class="c-pickup">
    <h2 class="c-pickup__title">PICKUP</h2>
    <div class="c-pickup__block">
      <Card1 :pickupData="pickupData"></Card1>
    </div>
  </section>
</template>

<script>
export default {
  props: ['pickupData']
}
</script>

<style lang="scss" scoped>
.c-pickup {
  padding: 220px 0 70px;
  margin-top: -150px;
  background: #f1f1f1;
  &__title {
    margin-bottom: 30px;
    text-align: center;
    font-size: 4rem;
    font-weight: normal;
  }
  &__block {
    width: 1200px;
    margin: auto;
    display: flex;
    justify-content: space-between;
    flex-wrap: wrap;
  }
}
</style>
