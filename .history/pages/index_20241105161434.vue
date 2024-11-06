<template>
  <el-container>
    <el-header>
      <Header />
    </el-header>

    <el-container>
      <el-aside width="200px" class="sidebar">
        <Navbar />
      </el-aside>
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
  height: 100vh; /* 使侧边栏充满整个视口高度 */
  padding: 20px; /* 为侧边栏添加内边距 */
  overflow: hidden; /* 隐藏滚动条 */
}
</style>