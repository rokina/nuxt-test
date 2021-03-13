<template>
  <section class="c-pickup">
    <h2 class="c-pickup__title">PICKUP</h2>
    <div class="c-pickup__block">
      <Card></Card>
      <Card></Card>
      <Card></Card>
      <Card></Card>
    </div>
  </section>
</template>

<style lang="scss" scoped>
.c-pickup {
  padding: 200px 0 70px;
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
