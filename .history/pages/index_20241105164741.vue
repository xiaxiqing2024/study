<template>
  <el-container>
    <el-header>
      <Header />
    </el-header>
    <el-container class="container" style="height: 100vh>
      <el-aside width="200px"><Navbar /></el-aside>
      <el-main>Main</el-main>
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
</style>