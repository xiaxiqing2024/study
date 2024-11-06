<!--
 * @Author: duyuran 940315806@qq.com
 * @Date: 2024-11-05 13:50:14
 * @LastEditors: duyuran 940315806@qq.com
 * @LastEditTime: 2024-11-05 14:40:28
 * @FilePath: \test\components\navbar.vue
 * @Description: 这是默认设置,请设置`customMade`, 打开koroFileHeader查看配置 进行设置: https://github.com/OBKoro1/koro1FileHeader/wiki/%E9%85%8D%E7%BD%AE
-->
<template>
  <el-row class="tac">
    <el-col :span="12">
      <h5>默认颜色</h5>
      <el-menu
        default-active="1"
        class="el-menu-vertical-demo"
        @open="handleOpen"
        @close="handleClose"
      >
        <el-submenu index="1">
          <template #title>
            <i class="el-icon-location"></i>
            <span>导航一</span>
          </template>
          <el-menu-item index="1-1">选项1</el-menu-item>
          <el-menu-item index="1-2">选项2</el-menu-item>
        </el-submenu>
        <el-menu-item index="2">
          <i class="el-icon-menu"></i>
          <span>导航二</span>
        </el-menu-item>
        <el-menu-item index="3" disabled>
          <i class="el-icon-document"></i>
          <span>导航三</span>
        </el-menu-item>
      </el-menu>
    </el-col>
    <el-col :span="12">
      <h5>自定义颜色</h5>
      <el-menu
        default-active="2"
        class="el-menu-vertical-demo"
        @open="handleOpen"
        @close="handleClose"
        background-color="#545c64"
        text-color="#fff"
        active-text-color="#ffd04b"
      >
        <el-submenu index="1">
          <template #title>
            <i class="el-icon-location"></i>
            <span>导航一</span>
          </template>
          <el-menu-item index="1-1">选项1</el-menu-item>
          <el-menu-item index="1-2">选项2</el-menu-item>
        </el-submenu>
        <el-menu-item index="2">
          <i class="el-icon-menu"></i>
          <span>导航二</span>
        </el-menu-item>
      </el-menu>
    </el-col>
  </el-row>
</template>
  
  <script>
export default {
  name: "Navbar",
  methods: {
    handleOpen(key, keyPath) {
      console.log("打开:", key, keyPath);
    },
    handleClose(key, keyPath) {
      console.log("关闭:", key, keyPath);
    },
  },
};
</script>
  
  <style scoped>
.tac {
  text-align: center; /* 中心对齐 */
}
.el-menu-vertical-demo {
  width: 100%; /* 设置菜单宽度 */
}
</style>