<template>
    <div>
        <headpage></headpage>
        <el-breadcrumb class="bread" separator-class="el-icon-arrow-right">
                <el-breadcrumb-item>首页</el-breadcrumb-item>
                <el-breadcrumb-item>博客文章</el-breadcrumb-item>
                <el-breadcrumb-item>文章详情</el-breadcrumb-item>
        </el-breadcrumb>
        <div class="blogInfo">
            <div class="blogInfo__info">
              <span class="blogInfo__info-title">{{blogs[this.id].title}}</span>
              <div class="n">
              <i class="el-icon-user"></i><span class="blogInfo__info-name">自己</span>
              <i class="el-icon-date"></i><span class="blogInfo__info-time">{{blogs[this.id].time}}</span>
              </div>
              <div class="m">
              <span>标签：</span><span class="blogInfo__info-tag" v-for="item in blogs[this.id].tags" :key="item">{{item}}</span>
              </div>
              <el-divider content-position="left">正文</el-divider>
              <span class="blogInfo__info-msg">&emsp;&emsp;{{blogs[this.id].msg}}</span>
              <div class="k">
                <span id="upTitle">点亮赞一下吧</span><i id="up" class="el-icon-s-opportunity" @click="up()"></i>
              </div>
            </div>
            <div class="blogInfo__other"></div>
        </div>
        <footpage></footpage>
    </div>
</template>
<script>
import headpage from '@/components/header'
import footpage from '@/components/footer'
export default {
  components: {
    headpage,
    footpage
  },
  data () {
    return {
      id: this.$route.query.id,
      flag: false,
      blogs: [
        {title: 'vue面试题', time: '2019-12-20 08:33', msg: '待更新', tags: ['Vue.js']},
        {title: 'es6新特性', time: '2022-08-08 14:30', msg: '待更新', tags: ['es6']},
        {title: 'js面试题', time: '2022-08-08 14:30', msg: '待更新', tags: ['js']},
        {title: 'css面试题', time: '2022-08-08 14:30', msg: ' 待更新', tags: ['css']}
      ]
    }
  },
  methods: {
    up () {
      this.flag = !this.flag
      if (this.flag === true) {
        $('#up').css('color', '#E6A23C')
        $('#upTitle').text('感谢您的鼓励').css('color', '#E6A23C')
      } else {
        $('#up').css('color', '#303133')
        $('#upTitle').text('点亮赞一下吧').css('color', '#67C23A')
      }
    }
  }
}
</script>
<style lang="less">
.bread{
    font-size: 18px;
    font-family: Helvetica Neue, Helvetica, Arial, sans-serif;
    color: #303133;
    margin: 2% 0 0 2%
  }
.blogInfo{
  position: relative;
  width: 70%;
  margin-left: 13%;
  &__info{
    background-color: rgba(216,226,235,0.8);
    padding: 2% 2% 2% 2%;
    border-radius: 10px;
    margin-top: 2%;
    &-title{
        font-family: "Microsoft YaHei";
        font-size: 22px;
        font-weight: 800;
        display: block;
        color: #303133;
        text-align: center;
    }
    .n{
        border: 1px dashed #E6A23C;
        padding: 0.5% 0 0.5% 0;
        margin-top: 2%;
        text-align: center;
    }
    .m{
        margin-top: 2%;
    }
    &-tag{
        background-color: rgba(3,101,100,0.7);
        color:aliceblue;
        display: inline-block;
        border-radius: 5px;
        padding: 0.5% 1% 0.5% 1%;
        margin: 0 0 0 1%;
    }
    .el-divider{
        background-color: aliceblue;
      }
    &-msg{
        font-size: 18px;
    }
    .k{
        font-size: 20px;
        text-align: center;
        margin-top: 2%;
        color: #67C23A;
        i{
            font-size: 25px;
            color: #303133;
        }
    }
  }
}
</style>
