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
    name: 'Header',
    data() {
      return {
        currentTime: '',
        userRole: '访客' // 你可以根据实际情况设置角色
      };
    },
    methods: {
      updateTime() {
        const now = new Date();
        this.currentTime = now.toLocaleString(); // 格式化当前时间
      }
    },
    mounted() {
      this.updateTime(); // 组件挂载时更新当前时间
      setInterval(this.updateTime, 1000); // 每秒更新时间
    },
    beforeDestroy() {
      clearInterval(this.updateTime); // 清除定时器
    }
  }
  </script>
  
  <style scoped>
  header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 10px;
    background-color: #f8f8f8;
  }
  
  .user-info {
    font-size: 14px;
  }
  </style>