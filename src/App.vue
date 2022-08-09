<template>
  <div id="app">
    <router-view/>
  </div>
</template>

<script>
export default {
  name: 'App',
  methods: {
    getHeight () {
      // 根据页面元素的总高度来设置背景的高度
      let height = document.documentElement.scrollHeight + 'px'
      $('.particle').css('height', height)
    }
  },
  mounted () {
    this.getHeight()
  },
  watch: {
    '$route' (to, from) { // 监听路由是否变化
      this.getHeight()
      location.reload()
    }
  }
}
</script>

<style>
.header {
  top: 0;
  width: 100%;
  position: fixed;
  z-index: 3;
}
* {
  padding: 0;
  margin: 0;
}
.particle{
      position: absolute;
      width: 100%;
      background-repeat: no-repeat;
      background-size: cover;
      background-position: 50% 50%;
}
</style>
