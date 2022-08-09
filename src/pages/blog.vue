<template>
    <div>
        <headpage></headpage>
        <div class="blog">
          <div class="blog__list">
            <div v-for="(item1, index1) in blogs" :key="index1" class="blog__list-one">
              <el-link class="blog__list-one__title" @click="to(index1)">{{item1.title}}</el-link>
              <i class="el-icon-date" style="margin-left:5%"></i><span>{{item1.time}}</span>
              <el-divider content-position="right">自己</el-divider>
              <span v-for="tag in item1.tags" :key="tag" class="blog__list-one__tag">{{tag}}</span>
              <span class="blog__list-one__msg">{{item1.msg}}</span>
              <i class="el-icon-view" style="color:#409EFF;margin-left:80%"></i><span class="blog__list-one__look">{{item1.look}}</span>
              <i class="el-icon-s-opportunity" style="color:#FFDC52;margin-left:3%"></i><span class="blog__list-one__up">{{item1.up}}</span>
            </div>
            <el-pagination
              style="margin:2% 0 0 20%"
              background
              layout="prev, pager, next"
              :total="1000">
            </el-pagination>
          </div>
          <div class="blog__other">
            <div class="blog__other-search">
              <el-input class="blog__other-search__in" v-model="msg" placeholder="搜索"></el-input>
              <el-button type="primary" icon="el-icon-search"></el-button>
            </div>
            <div class="blog__other-tags">
              <h4 class="el-icon-s-order">公告</h4>
              <el-divider><i class="el-icon-collection-tag"></i></el-divider>
              <span>{{tags}}</span>
            </div>
          </div>
        </div>
        <footpage></footpage>
    </div>
</template>
<script>
import headpage from '@/components/header'
import footpage from '@/components/footer'
export default {
  data () {
    return {
      msg: '',
      tags: '半成品，后续会完善其他功能，未适配移动端',
      blogs: [
        {title: 'vue面试题', time: '2022-02-20 08:33', msg: 'vue面试题', look: 300, up: 12, tags: ['Vue.js']},
        {title: 'es6新特性', time: '2022-02-20 09:43', msg: '待更新', look: 212, up: 10, tags: ['es6']},
        {title: 'js面试题', time: '2022-02-20 09:20', msg: '待更新', look: 312, up: 28, tags: ['JavaScript']},
        {title: 'css面试题', time: '2022-02-20 14:30', msg: '待更新', look: 1212, up: 100, tags: ['css']}
      ]
    }
  },
  components: {
    headpage,
    footpage
  },
  methods: {
    to (index1) {
      this.$router.push({path: '/blogInfo?id=' + index1})
    }
  }
}
</script>
<style lang="less" scoped>
.blog{
  margin-top: 40px;
  position: relative;
  display: flex;
  flex-direction: row;
  &__list{
    width: 70%;
    margin: 2% 0 0 2%;
    padding: 0 2% 0 2%;
    &-one{
      background-color: rgba(216,226,235,0.8);
      padding: 2% 2% 2% 2%;
      border-radius: 10px;
      margin-top: 2%;
      .el-divider{
        background-color: aliceblue;
      }
      &__title{
        font-family: "Microsoft YaHei";
        font-size: 25px;
      }
      &__tag{
        background-color: rgba(3,101,100,0.7);
        color:aliceblue;
        display: inline-block;
        border-radius: 5px;
        padding: 0.5% 1% 0.5% 1%;
        margin: 0 0 0 1%;
      }
      &__msg{
        display: block;
        font-family: '宋体';
        padding: 2% 1% 2% 2%;
      }
    }
  }
  &__other{
    width: 25%;
    margin: 2% 2% 0 2%;
    &-search{
      margin-top: 8%;
      text-align: center;
      &__in{
        width: 50%
      }
    }
    &-tags{
      background-color: rgba(22,183,150,0.8);
      border-radius: 10px;
      padding: 0.5% 2% 4% 2%;
      margin-top: 10%;
      font-family: "Microsoft YaHei";
      color: aliceblue;
      height: 150px;
      h4{
        padding-top: 10px;
        padding-left:10px;
      }
      span{
        padding: 1% 1% 1% 1%;
        margin: 1% 0 0 4%;
        display: inline-block;
        border-radius: 4px;
      }
    }
  }
}
</style>
