<template>
    <header class="header">
      <h1 class="site-title">我的网站标题</h1>
      <div class="right-content">
        <span class="current-time">{{ currentTime }}</span>
        <span class="user-role">{{ userRole }}</span>
      </div>
    </header>
  </template>
  
  <script>
  export default {
    name: 'Header',
    data() {
      return {
        currentTime: this.getCurrentTime(), // 初始化当前时间
        userRole: '访客' // 设置用户角色
      };
    },
    methods: {
      getCurrentTime() {
        const now = new Date();
        return now.toLocaleString(); // 格式化当前时间
      }
    },
    mounted() {
      // 每秒更新当前时间
      setInterval(() => {
        this.currentTime = this.getCurrentTime();
      }, 1000);
    },
    beforeDestroy() {
      clearInterval(this.updateTime); // 清除定时器
    }
  }
  </script>
  
  <style scoped>
  .header {
    background-color: #315c88; /* 自定义背景颜色 */
    color: white; /* 字体颜色 */
    height: 60px; /* 设置头部高度 */
    line-height: 60px; /* 垂直居中 */
    display: flex; /* 使用 Flexbox 布局 */
    justify-content: space-between; /* 在两端对齐 */
    align-items: center; /* 垂直居中对齐 */
    padding: 0 20px; /* 左右内边距 */
    position: fixed; /* 固定在顶部 */
    top: 0; /* 距离顶部0 */
    left: 0; /* 距离左边0 */
    right: 0; /* 距离右边0 */
    z-index: 1000; /* 确保在其他元素上方 */
  }
  
  .site-title {
    margin: 0; /* 去掉默认外边距 */
  }
  
  .right-content {
    display: flex; /* 使用 Flexbox 布局 */
    align-items: center; /* 垂直居中对齐 */
  }
  
  .current-time {
    margin-right: 20px; /* 时间与角色之间的间距 */
  }
  </style>