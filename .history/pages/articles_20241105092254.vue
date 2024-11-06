<template>
  <div>
    <h1>文章列表</h1>
    <ul>
      <li v-for="article in articles" :key="article.slug">
        <h2>{{ article.title }}</h2>
        <p>{{ article.description }}</p>
      </li>
    </ul>
  </div>
</template>
  
  <script>
export default {
  data() {
    return {
      articles: [],
    };
  },
  async fetch() {
    try {
      const response = await this.$axios.$get("/articles");
      this.articles = response.articles;
    } catch (error) {
      console.error(
        "Error fetching articles:",
        error.response ? error.response.data : error.message
      );
      if (error.response) {
        console.error("Response status:", error.response.status);
        console.error("Response headers:", error.response.headers);
      }
    }
  },
};
</script>
  
  <style scoped>
/* 样式 */
</style>