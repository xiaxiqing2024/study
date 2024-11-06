<!--
 * @Author: duyuran 940315806@qq.com
 * @Date: 2024-11-04 19:44:07
 * @LastEditors: duyuran 940315806@qq.com
 * @LastEditTime: 2024-11-05 14:46:30
 * @FilePath: \test\pages\index.vue
 * @Description: 这是默认设置,请设置`customMade`, 打开koroFileHeader查看配置 进行设置: https://github.com/OBKoro1/koro1FileHeader/wiki/%E9%85%8D%E7%BD%AE
-->
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