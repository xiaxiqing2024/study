<template>
  <el-container style="height: 100vh">
    <el-header>
      <Header />
    </el-header>
    <el-container>
      <el-aside width="200px">
        <Navbar /> <!-- 导航栏 -->
      </el-aside>
      <el-main>
        <nuxt-child /> <!-- 确保在这里渲染子路由 -->
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
};
</script>

<style>
/* 样式 */
</style>