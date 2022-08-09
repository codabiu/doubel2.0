<template>
    <div class="footer">
        Copyright © double All Rights Reserved.
    </div>
</template>
<script>
export default {
  methods: {
    getH () {
      let height = document.documentElement.scrollHeight > window.screen.height ? document.documentElement.scrollHeight : window.screen.height + 'px'
      if (height === document.documentElement.scrollHeight + 'px') {
        $('.footer').css('margin-top', '10px')
      } else {
        $('.footer').css('margin-top', '5%')
      }
    }
  },
  mounted () {
    this.getH()
  }
}
</script>
<style lang="less">
.footer{
    width: 100%;
    font-family: '微软雅黑';
    text-align: center;
    font-size: 16px;
    background-color: #2C3E51;
    color: aliceblue;
    height: 60px;
    line-height: 60px;
}
</style>
