<template>
    <section class="container">
      <div>
        <el-radio v-model="radio" label="1">备选项</el-radio>
        <el-radio v-model="radio" label="2">备选项</el-radio>
        <app-logo />
        <h1 class="title">欢迎</h1>
        <h2 class="subtitle">一个 nuxt 工程</h2>
        <div class="links">
          <a href="https://nuxtjs.org/" target="_blank" class="button--green">
            博客园
          </a>
          <a
            href="https://github.com/nuxt/nuxt.js"
            target="_blank"
            class="button--grey"
            >GitHub</a
          >
        </div>
      </div>
    </section>
  </template>
  
  <script>

  export default {
    components: {
    },
    data() {
      return {
        radio: "1",
      };
    },
  };
  </script>