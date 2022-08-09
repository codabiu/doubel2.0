<template>
  <div class="header">
    <el-menu
      :default-active="this.$route.path"
      router
      mode="horizontal"
      background-color="#fff"
      text-color="#303133"
      active-text-color="#409EFF"
    >
      <el-menu-item v-for="(item,i) in navList" :key="i" :index="item.name" :class="item.icon">
        {{ item.navItem }}
      </el-menu-item>
    </el-menu>
  </div>
</template>
<script>
export default {
  data () {
    return {
      navList: [
        {name: '', class: 'name', navItem: 'double', icon: 'el-icon-s-promotion'},
        {name: '/', class: 'index', navItem: '首页', icon: 'el-icon-s-home'},
        {name: '/blog', class: 'blog', navItem: '文章公告', icon: 'el-icon-document-remove'},
        {name: '/schedule', class: 'schedule', navItem: '待办事项', icon: 'el-icon-collection-tag'},
        {name: '/about_me', class: 'about_me', navItem: '关于我', icon: 'el-icon-user-solid'},
        {name: '/message', class: 'message', navItem: '留言板', icon: 'el-icon-s-comment'}
      ]
    }
  },
  methods: {
  }
}
</script>

<style lang="less" scoped>
  .el-icon-s-promotion {
    font-size: 18px;
    font-family: Helvetica Neue, Helvetica, Arial, sans-serif;
  }
  .el-icon-s-home,.el-icon-document-remove, .el-icon-collection-tag, .el-icon-user-solid, .el-icon-s-comment{
    font-size: 15px;
  }
  .el-icon-s-home{
      margin-left: 5%
  }
</style>
