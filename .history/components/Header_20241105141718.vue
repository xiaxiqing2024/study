<template>
  <header>
    <h1>我的网站标题</h1>
    <div class="user-info">
      <span>当前时间: {{ currentTime }}</span>
      <span>角色: {{ userRole }}</span>
    </div>
  </header>
</template>
  
  <script>
export default {
  name: "Header",
  data() {
    return {
      currentTime: "",
      userRole: "访客", // 你可以根据实际情况设置角色
    };
  },
  methods: {
    updateTime() {
      const now = new Date();
      this.currentTime = now.toLocaleString(); // 格式化当前时间
    },
  },
  mounted() {
    this.updateTime(); // 组件挂载时更新当前时间
    setInterval(this.updateTime, 1000); // 每秒更新时间
  },
  beforeDestroy() {
    clearInterval(this.updateTime); // 清除定时器
  },
};
</script>
  
  <style scoped>
.header {
  background-color: #409eff; /* 自定义背景颜色 */
  color: white; /* 字体颜色 */
  height: 60px; /* 设置头部高度 */
  line-height: 60px; /* 垂直居中 */
  text-align: center; /* 文本居中 */
  position: fixed; /* 固定在顶部 */
  top: 0; /* 距离顶部0 */
  left: 0; /* 距离左边0 */
  right: 0; /* 距离右边0 */
  z-index: 1000; /* 确保在其他元素上方 */
}

.user-info {
  font-size: 14px;
}
</style>