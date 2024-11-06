<template>
  <el-container>
    <el-header>
      <Header />
    </el-header>

    <el-container>
      <el-aside width="200px"> 
        <Navbar />
      </el-aside>
      <el-main>Main</el-main>
    </el-container>

  </el-container>
</template>

  <script>
import Header from "@/components/Header.vue";
import Navbar from "../components/navbar.vue";

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