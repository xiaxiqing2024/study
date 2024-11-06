<!--
 * @Author: duyuran 940315806@qq.com
 * @Date: 2024-11-04 19:44:07
 * @LastEditors: duyuran 940315806@qq.com
 * @LastEditTime: 2024-11-05 09:22:26
 * @FilePath: \test\pages\articles.vue
 * @Description: 这是默认设置,请设置`customMade`, 打开koroFileHeader查看配置 进行设置: https://github.com/OBKoro1/koro1FileHeader/wiki/%E9%85%8D%E7%BD%AE
-->
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