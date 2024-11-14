<template>
  <div class="breadcrumb">
    <el-breadcrumb separator="/">
      <el-breadcrumb-item v-for="(item, index) in breadcrumbItems" :key="index">
        <nuxt-link v-if="item.route" :to="item.route">{{
          item.label
        }}</nuxt-link>
        <span v-else>{{ item.label }}</span>
      </el-breadcrumb-item>
    </el-breadcrumb>
  </div>
</template>
  
<script>
export default {
  name: "Breadcrumb",
  computed: {
    breadcrumbItems() {
      // 获取当前路由路径
      const pathArray = this.$route.path.split("/").filter((path) => path);

      // 生成面包屑项
      return pathArray
        .map((path, index) => {
          const route = "/" + pathArray.slice(0, index + 1).join("/");
          return {
            label: this.capitalize(path), // 首字母大写
            route: route, // 拼接路径
          };
        })
        .concat([{ label: "当前页面" }]); // 添加当前页面项
    },
  },
  methods: {
    capitalize(str) {
      // 首字母大写的辅助函数
      return str.charAt(0).toUpperCase() + str.slice(1);
    },
  },
};
</script>
  
<style>
.breadcrumb {
  margin: 20px 0; /* 增加上下边距 */
}
</style>