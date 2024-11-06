<template>
    <div class="sidebar">
      <h2>菜单</h2>
      <ul>
        <li><nuxt-link to="/">首页</nuxt-link></li>
        <li><nuxt-link to="/test">测试</nuxt-link></li>
      </ul>
    </div>
  </template>
  
  <script>
  export default {
    name: 'Sidebar',
  }
  </script>
  
  <style scoped>
  .sidebar {
    width: 250px;
    height: 100vh;
    background-color: #f4f4f4;
    padding: 20px;
    position: fixed;
    left: 0;
    top: 0;
    box-shadow: 2px 0 5px rgba(0, 0, 0, 0.1);
  }
  
  .sidebar ul {
    list-style: none;
    padding: 0;
  }
  
  .sidebar li {
    margin: 15px 0;
  }
  
  .sidebar a {
    text-decoration: none;
    color: #333;
  }
  
  .sidebar a:hover {
    color: #007bff;
  }
  </style>