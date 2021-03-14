<template>
  <!-- https://bamp.media/ -->
  <div>
    <Header></Header>
    <main>
      <Slider></Slider>
      <Pickup></Pickup>
      <div class="c-container">
        <MainConts :postsData="contents"></MainConts>
        <Sidebar></Sidebar>
      </div>
    </main>
  </div>
</template>

<script>
import axios from 'axios'
import MainConts from '/components/MainConts'

export default {
  async asyncData({ $config }) {
    const { data } = await axios.get(
      'https://headless-test.microcms.io/api/v1/news',
      {
        headers: { 'X-API-KEY': $config.apiKey }
      }
    )
    return data
  },
  components: {
    MainConts: MainConts //必要ない？
  }
}
</script>

<style lang="scss" scoped>
.c-container {
  margin: 100px auto 0;
  width: 1200px;
  display: flex;
  flex-wrap: wrap;
}
</style>
