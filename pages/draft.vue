<template>
  <div>
    <Header></Header>
    <main>
      <div class="c-container">
        <div class="c-conts">
          <p class="c-label">{{ data.category && data.category.name }}</p>
          <h1 class="c-title">{{ data.title }}</h1>
          test
          <p class="c-date">
            {{ $moment(data.publishedAt).format('YYYY.MM.DD') }}
          </p>
          <div class="c-post" v-html="data.body"></div>
        </div>
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
      data: {}
    }
  },
  async created() {
    const query = this.$route.query
    if (query.id === undefined || query.draftKey === undefined) {
      return
    }
    const { data } = await axios.get(
      `https://headless-test.microcms.io/api/v1/news/${query.id}?draftKey=${query.draftKey}`,
      {
        headers: { 'X-API-KEY': '824d2944-2a90-40b2-9097-78dfb1570015' }
      }
    )
    this.data = data
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
