<template>
  <!-- https://bamp.media/ -->
  <div>
    <Header></Header>
    <main>
      <Slider></Slider>
      <Pickup></Pickup>
      <div class="c-container">
        <MainConts :postsData="posts"></MainConts>
        <Sidebar></Sidebar>
      </div>
    </main>
    <Footer></Footer>
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
    const { data:data2 } = await axios.get(
      'https://headless-test.microcms.io/api/v1/pickup/99ggpm7e16',
      {
        headers: { 'X-API-KEY': $config.apiKey }
      }
    )
    // console.log(data2)
    return { posts: data.contents, pickup: data2.pickup_post }
  },
  components: {
    MainConts
  }
}
</script>

<style lang="scss" scoped>
.c-container {
  margin: 100px auto;
  width: 1200px;
  display: flex;
  flex-wrap: wrap;
}
</style>
