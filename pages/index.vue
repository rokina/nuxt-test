<template>
  <!-- https://bamp.media/ -->
  <div>
    <Header></Header>
    <main>
      <Slider></Slider>
      <Pickup :pickupData="pickup"></Pickup>
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
import Pickup from '/components/Pickup'

export default {
  async asyncData({ $config }) {
    const { data:posts } = await axios.get(
      'https://headless-test.microcms.io/api/v1/news',
      {
        headers: { 'X-API-KEY': $config.apiKey }
      }
    )
    const { data:pickup } = await axios.get(
      'https://headless-test.microcms.io/api/v1/pickup/99ggpm7e16?depth=2',
      {
        headers: { 'X-API-KEY': $config.apiKey }
      }
    )
    // console.log(pickup)
    return { posts: posts.contents, pickup: pickup.pickup_post }
  },
  components: {
    MainConts,
    Pickup
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
