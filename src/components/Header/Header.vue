<template>
  <div class="header">
    <div class="headerTop">
      <a href="##" class="title"></a>
      <div class="searchInput">
        <i class="iconfont icon-fangdajing"></i>
        <span>搜索商品,共27017件好物</span>
      </div>
      <button class="btn">登录</button>
    </div>
    <div class="tabWap">
      <div class="headerCatgory">
        <ul class="CatgoryList" >
          <li class="on">推荐</li>
          <li>居家生活</li>
          <li>服饰鞋包</li>
          <li>美食酒水</li>
          <li>居家生活</li>
          <li>居家生活</li>
          <li>居家生活</li>
          <li>居家生活</li>
          <li>全球特色</li>
        </ul>
      </div>
      <div class="toggleWrap">
        <div class="linear"></div>
        <div class="toggle">
          <img src="../../../static/imgs/icon-jiantou.png" alt=""
               ref="arrow" @click="toggleUPDown">
        </div>
      </div>
      <div class="wrapList" v-show="isUp===true">
        <p>全部频道</p>
        <ul>
          <li>居家生活</li>
          <li>服饰鞋包</li>
          <li>美食酒水</li>
          <li>居家生活</li>
          <li>居家生活</li>
          <li>居家生活</li>
          <li>居家生活</li>
          <li>全球特色</li>
          <li>全球特色</li>
        </ul>
      </div>
    </div>
  </div>
</template>
<script>
  import BScroll from 'better-scroll'
  export default{
    data(){
      return{
         isUp:false
      }
    },
    mounted(){
      new BScroll('.headerCatgory', {
        click: true,
        scrollX: true
      })
    },
    methods:{
      toggleUPDown(){
        this.isUp = !this.isUp
        if (this.isUp){
          this.$refs.arrow.style.transform='rotate(180deg)'
        }else{
          this.$refs.arrow.style.transform='rotate(-360deg)'
        }
      }
    }
  }
</script>
<style scoped lang="stylus" rel="stylesheet/stylus">
  .header
    .headerTop
      display flex
      align-items center
      width 100%
      height: 88px

      .title
        display: inline-block
        width 138px
        height 40px
        background-image url(//yanxuan-static.nosdn.127.net/hxm/yanxuan-wap/p/20161201/style/img/icon-normal/indexLogo-a90bdaae6b.png)
        background-size 100%
        background-repeat no-repeat
        margin-left 40px
        margin-right 20px
      .searchInput
        width 57%
        height 56px
        border-radius 10px
        background #ededed
        color #666
        line-height 56px
        margin-right 20px
        i
          margin-left 20px
          margin-right 10px
        span
          font-size: 0.37333rem
      .btn
        margin: 0;
        padding: 0;
        border: 1px solid #b4282d;  //自定义边框
        outline: none;
        width 74px
        height 40px
        line-height 40px
        font-size 0.32rem
        background white
        color #b4282d
        border-radius 10px

    .tabWap
      width 100%
      height 60px
      position relative
      .headerCatgory
        width 650px
        height: 60px
        overflow hidden
        .CatgoryList
          width 1300px
          float left
          height 60px
          line-height 60px
          li
            float left
            white-space nowrap
            font-size 0.37333rem
            padding 0 .21333rem
            color: #333
            &.on
              border-bottom 0.06rem solid #f00

      .toggleWrap
        width 160px
        height 60px
        position absolute
        right 0px
        bottom 0
        overflow hidden
        z-index 10
        .linear
          width 60px
          height 60px
          float left
          background white
        .toggle
          width 100px
          height 60px
          float right
          line-height 70px
          text-align center
          background white

      .wrapList
        position absolute
        left 0
        top 0
        background white
        z-index 5
        P
          height 60px
          line-height 60px
          font-size 30px
          padding-left 30px
        ul
          display flex
          flex-wrap wrap
          justify-content flex-start
          padding-left 30px
          li
            width 165px
            height 60px
            line-height 60px
            margin 7.5px
            padding 0 16px
            box-sizing border-box
            font-size 30px
            color #333
            border 2px solid #d9d9d9
            border-radius 10px
            display flex
            justify-content center
            background #FAFAFA
</style>
