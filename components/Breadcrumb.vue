<template>
  <div>
    <el-breadcrumb>
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
      const pathArray = this.$route.path.split("/").filter((path) => path);
      const pathNames = {
        energy: "能源",
      };
      return pathArray
        .map((path, index) => {
          const route = "/" + pathArray.slice(0, index + 1).join("/");
          return {
            label: pathNames[path] || this.capitalize(path),
            route: route,
          };
        })
        .concat([{ label: "当前页面" }]);
    },
  },
  methods: {
    capitalize(str) {
      return str.charAt(0).toUpperCase() + str.slice(1);
    },
  },
};
</script>
  
</style>