<template>
  <div class="container">
    <el-row>
      <el-col :span="4" class="sidebar">
        <h5>默认颜色</h5>
        <el-menu
          default-active="2"
          class="el-menu-vertical-demo"
          @open="handleOpen"
          @close="handleClose">
          <el-submenu index="1">
            <template slot="title">
              <i class="el-icon-location"></i>
              <span>导航一</span>
            </template>
            <el-menu-item-group>
              <template slot="title">分组一</template>
              <el-menu-item index="1-1">选项1</el-menu-item>
              <el-menu-item index="1-2">选项2</el-menu-item>
            </el-menu-item-group>
            <el-menu-item-group title="分组2">
              <el-menu-item index="1-3">选项3</el-menu-item>
            </el-menu-item-group>
            <el-submenu index="1-4">
              <template slot="title">选项4</template>
              <el-menu-item index="1-4-1">选项1</el-menu-item>
            </el-submenu>
          </el-submenu>
          <el-menu-item index="2">
            <i class="el-icon-menu"></i>
            <span slot="title">导航二</span>
          </el-menu-item>
          <el-menu-item index="3" disabled>
            <i class="el-icon-document"></i>
            <span slot="title">导航三</span>
          </el-menu-item>
          <el-menu-item index="4">
            <i class="el-icon-setting"></i>
            <span slot="title">导航四</span>
          </el-menu-item>
        </el-menu>
      </el-col>
      <el-col :span="20">
        <div class="content">
          <h2>主内容区</h2>
          <p>这里是主内容区域，可以根据需要填充内容。</p>
        </div>
      </el-col>
    </el-row>
  </div>
</template>

<script>
export default {
  name: 'Navbar',
  methods: {
    handleOpen(key, keyPath) {
      console.log(key, keyPath);
    },
    handleClose(key, keyPath) {
      console.log(key, keyPath);
    }
  }
}
</script>

<style>
.container {
  height: 100vh; /* 使容器充满整个视口 */
}

.sidebar {
  background-color: #f4f4f4; /* 左侧导航条背景色 */
  padding: 20px; /* 内边距 */
  height: 100%; /* 使导航条高度充满父容器 */
}

.content {
  padding: 20px; /* 主内容区的内边距 */
}
</style>