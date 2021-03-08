<template>
  <main class="main">
    <h1 class="title">{{ title }}</h1>
    <p class="publishedAt">{{ publishedAt }}</p>
    <p class="category">{{ category && category.name }}</p>
    <div class="post" v-html="body"></div>
  </main>
</template>

<script>
import axios from 'axios'
export default {
  async asyncData({ params }) {
    const { data } = await axios.get(
      `https://headless-test.microcms.io/api/v1/news/${params.slug}`,
      {
        headers: { 'X-API-KEY': '824d2944-2a90-40b2-9097-78dfb1570015' }
      }
    )
    return data
  }
}
</script>
