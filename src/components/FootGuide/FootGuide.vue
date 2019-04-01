<template>
  <div class="footer">
    <ul class="foot-wrap">
      <li @click="goto('/firstView')" :class="{active:$route.path==='/firstView'}">
        <i class="iconfont icon-552cd5641bbec"></i>
        <span>首页</span>
      </li>
      <li @click="goto('/catgory')" :class="{active:$route.path==='/catgory'}">
        <i class="iconfont icon-classifi"></i>
        <span>分类</span>
      </li>
      <li @click="goto('/knowArticle')" :class="{active:$route.path==='/knowArticle'}">
        <i class="iconfont icon-tupian"></i>
        <span>识物</span>
      </li>
      <li @click="goto('/shopCards')" :class="{active:$route.path==='/shopCards'}">
        <i class="iconfont icon-caigou-xianxing"></i>
        <span class="shopCard">购物车</span>
      </li>
      <li @click="goto('/personal')" :class="{active:$route.path==='/personal'}">
        <i class="iconfont icon-jingjirenjinglikehuxianxingcopy"></i>
        <span>个人</span>
      </li>
    </ul>
  </div>
</template>
<script>
  export default{
    methods:{
      goto(path){
        //编程式路由导航 替换掉之前的路径
        this.$router.replace(path)
      }
    }
  }
</script>
<style scoped lang="stylus" rel="stylesheet/stylus">
  .footer
    border-top 2px solid #d9d9d9
    position fixed
    left 0
    bottom 0
    width 100%
    height 80px
    background white
    z-index 10
    .foot-wrap
      display flex
      justify-content space-around

      li
        width 74px
        height 74px
        text-align center
        display flex
        flex-direction column
        justify-content center
        color: #7F7F7F
        &.active
          color #b4282d
        i
          font-size 40px
          margin-top 10px
          width 100%
          height 100%
        span
           margin-top 5px
           width 100%
           height 100%
</style>
