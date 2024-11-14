<template>
  <el-container style="height: 100vh">
    <el-header>
      <Header />
    </el-header>
    <el-container>
      <el-aside width="200px">
        <Navbar />
        <!-- 导航栏 -->
      </el-aside>
      <el-container class="container_demo">
        <el-header>
          <Breadcrumb />
        </el-header>
        <el-main class="container_test">
          <nuxt-child />
          <!-- 确保在这里渲染子路由 -->
        </el-main>
      </el-container>
    </el-container>
  </el-container>
</template>

<script>
import Header from "@/components/Header.vue";
import Navbar from "@/components/Navbar.vue";
import Breadcrumb from "@/components/Breadcrumb.vue";

export default {
  components: {
    Header,
    Navbar,
    Breadcrumb,
  },
};
</script>

<style>
.container_demo {
  background: linear-gradient(to bottom, #466a90, #ffffff); /* 自定义背景颜色 */
}
.container_test {
  background-color: #3b73ac; /* 自定义背景颜色 */
}
</style>