<template>
  <div>
    <Header></Header>
    <main>
      <div class="c-container">
        <MainConts :postsData="posts"></MainConts>
        <Sidebar></Sidebar>
      </div>
      <Pager></Pager>
    </main>
    <Footer></Footer>
  </div>
</template>

<script>
import axios from 'axios'
import MainConts from '/components/MainConts'

export default {
  async asyncData({ params, $config }) {
    const page = params.p || '1'
    const limit = 8
    const { data:posts } = await axios.get(
      `https://headless-test.microcms.io/api/v1/news?limit=${limit}&offset=${(page - 1) * limit}`,
      {
        headers: { 'X-API-KEY': $config.apiKey }
      }
    )
    return { posts: posts.contents}
  },
  components: {
    MainConts
  }
}
</script>

<style lang="scss" scoped>
.c-container {
  margin: 0 auto 100px;
  width: 1200px;
  display: flex;
  flex-wrap: wrap;
}
.c-pager {
  margin-bottom: 50px;
}
</style>
