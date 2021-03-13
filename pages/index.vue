<template>
  <!-- https://bamp.media/ -->
  <div>
    <Header></Header>
    <main>
      <Slider></Slider>
      <Pickup></Pickup>
      <div>
        <MainConts></MainConts>
        <Sidebar></Sidebar>
      </div>
      <ul>
        <li v-for="content in contents" :key="content.id">
          <nuxt-link :to="`/${content.id}`">
            {{ content.title }}
          </nuxt-link>
        </li>
      </ul>
    </main>
  </div>
</template>

<script>
import axios from 'axios'
export default {
  async asyncData({ $config }) {
    const { data } = await axios.get(
      'https://headless-test.microcms.io/api/v1/news',
      {
        headers: { 'X-API-KEY': $config.apiKey }
      }
    )
    return data
  }
}
</script>
