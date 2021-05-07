<template>
  <div>
    <Header></Header>
    <main>
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

export default {
  data() {
    return {
      posts: {}
    }
  },
  async created() {
    const keyword = this.$route.query.q

    const { data } = await axios.get(
      `https://headless-test.microcms.io/api/v1/news?q=${keyword}`,
      {
        // TODO: APIキー隠蔽できないか考える そもそも隠蔽の必要ある？
        headers: { 'X-API-KEY': '824d2944-2a90-40b2-9097-78dfb1570015' }
      }
    )
    this.posts = data.contents
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
.c-conts {
  width: 900px;
}
.c-label {
  color: #fff;
  font-size: 1.2rem;
  background: #000;
  display: inline-block;
  padding: 2px 10px;
}
.c-title {
  font-weight: normal;
  margin-top: 20px;
}
.c-date {
  margin-top: 15px;
  font-size: 1.4rem;
  color: #666;
}
.c-post {
  margin-top: 80px;
  position: relative;
  &::before {
    content: '';
    position: absolute;
    top: -50px;
    left: 0;
    width: 30px;
    height: 1px;
    background: #333;
  }
  h2 {
    color: #f00;
  }
}
</style>
