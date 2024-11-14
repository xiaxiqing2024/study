<template>
  <div class="container">
    <el-row class="tac">
      <el-col :span="4" class="sidebar">
        <el-menu
          class="el-menu-demo"
          :default-active="activeIndex"
          @open="handleOpen"
          @close="handleClose"
        >
          <el-submenu index="1">
            <template slot="title">
              <i class="el-icon-location"></i>
              <span>导航一</span>
            </template>
            <el-menu-item-group>
              <el-menu-item index="1-1" @click="setActive('1-1')">
                <nuxt-link to="/energy/index">选项1</nuxt-link>
              </el-menu-item>
              <el-menu-item index="1-2" @click="setActive('1-2')"
                >选项2</el-menu-item
              >
              <el-menu-item index="1-3" @click="setActive('1-3')"
                >选项3</el-menu-item
              >
            </el-menu-item-group>
          </el-submenu>
        </el-menu>
      </el-col>
    </el-row>
  </div>
</template>

<script>
export default {
  name: "Navbar",
  data() {
    return {
      activeIndex: "1-1", // 默认激活选项
    };
  },
  methods: {
    setActive(index) {
      this.activeIndex = index; // 更新激活的菜单项
    },
    handleOpen(key, keyPath) {
      console.log(key, keyPath);
    },
    handleClose(key, keyPath) {
      console.log(key, keyPath);
    },
  },
};
</script>

<style>
.container {
  display: flex; /* 使用 Flexbox 来布局 */
}

.tac {
  margin: 0; /* 确保没有外边距 */
}

.sidebar {
  padding: 20px; /* 为侧边栏添加内边距 */
  height: 100vh; /* 使导航条充满整个视口高度 */
}

.el-menu-demo {
  border-right: none; /* 移除右边框 */
}
</style>