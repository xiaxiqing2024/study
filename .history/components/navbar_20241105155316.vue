<template>
  <el-row class="tac">
    <el-col :span="12">
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
            <el-menu-item index="1-1" @click="setActive('1-1')"
              >选项1</el-menu-item
            >
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
</template>

<script>
export default {
  name: "Navbar",
  data() {
    return {
      activeIndex: '1-1', // 默认激活选项
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
.tac {
  margin-left: 0;
}
.el-menu-demo{
  margin-left: 0;
}
</style>