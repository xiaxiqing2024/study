<template>
  <el-container style="height: 100vh">
    <el-header>
      <Header />
    </el-header>
    <el-container class="container">
      <el-aside width="200px"><Navbar /></el-aside>
      <el-main
        >
        1233456
        <nuxt-child />
        <!-- 显示当前路由的子页面 -->
      </el-main>
    </el-container>
  </el-container>
</template>

  <script>
import Header from "@/components/Header.vue";
import Navbar from "@/components/Navbar.vue";

export default {
  components: {
    Header,
    Navbar,
  },
  data() {
    return {};
  },
};
</script>

<style>
.sidebar {
  height: 100%; /* 使侧边栏充满父容器高度 */
  padding: 20px; /* 为侧边栏添加内边距 */
}

.el-container {
  display: flex; /* 使用 Flexbox 布局 */
  justify-content: flex-start; /* 向左对齐 */
}
body > .el-container {
  margin-bottom: 40px;
}
.main-container {
  display: flex; /* 使用 Flexbox 布局 */
  height: 100%; /* 确保子容器的高度 */
}
</style>