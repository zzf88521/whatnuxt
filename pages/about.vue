<template>
  <section class="container">
    <img src="../assets/img/logo.png" alt="Nuxt.js Logo" class="logo" />
    <h1 class="title">
      此页面从 {{ name }} 加载
    </h1>
    <h2 class="info" v-if="name === 'client'">
      请刷新页面
    </h2>
    <nuxt-link class="button" to="/">
      首页
    </nuxt-link>
  </section>
</template>
<script>
export default {
  data ({ req }) {
    return {
      name: req ? '服务端' : '客户端'
    }
  },
  head () {
    return {
      title: `关于我们 (${this.name}-side)`
    }
  }
}
</script>

<style scoped>
.title
{
  margin-top: 50px;
}
.info
{
  font-weight: 300;
  color: #9aabb1;
  margin: 0;
  margin-top: 10px;
}
.button
{
  margin-top: 50px;
}
</style>
