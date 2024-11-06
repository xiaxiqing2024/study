<template>
  <header class="header">
    <div class="header-content">
      <h1>我的网站标题</h1>
      <span class="current-time">{{ currentTime }}</span>
    </div>
  </header>
</template>
  
  <script>
export default {
  name: "Header",
  data() {
    return {
      currentTime: this.getCurrentTime(), // 初始化当前时间
    };
  },
  methods: {
    getCurrentTime() {
      const now = new Date();
      return now.toLocaleString(); // 格式化当前时间
    },
  },
  mounted() {
    // 每秒更新当前时间
    setInterval(() => {
      this.currentTime = this.getCurrentTime();
    }, 1000);
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
  display: flex; /* 使用 Flexbox 布局 */
  justify-content: space-between; /* 在两端对齐 */
  align-items: center; /* 垂直居中对齐 */
  padding: 0 20px; /* 左右内边距 */
}

.header-content {
  display: flex; /* 使用 Flexbox 布局 */
  align-items: center; /* 垂直居中对齐 */
}

.current-time {
  margin-left: 20px; /* 标题与时间之间的间距 */
}
</style>