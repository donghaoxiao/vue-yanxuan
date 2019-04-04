<template>
  <div class="contentMessage">
    <div class="recommend_box">
      <ul>
        <li v-for="(topPic,index) in getTopPics" :key="index">
          <div class="left_right_box" v-if="topPic.style===2">
            <div class="wrapper">
              <div class="left_box">
                <div class="line1">
                  <img :src="topPic.avatar" alt="">
                  <span>{{topPic.nickname}}</span>
                </div>
                <div class="line2">
                  {{topPic.title}}
                </div>
                <div class="line3">
                  {{topPic.subTitle}}
                </div>
                <div class="line4">
                  <span class="iconfont icon-fangdajing"></span>
                  <span>{{topPic.readCount}}人看过</span>
                </div>
              </div>
              <img :src="topPic.picUrl" alt="">
            </div>
            <div class="split_box"></div>
          </div>
          <div class="line_show_box" v-if="topPic.style===1">
            <div class="line1">
              <img :src="topPic.avatar" alt="">
              <span>{{topPic.nickname}}</span>
            </div>
            <div class="line2">
              {{topPic.title}}
            </div>
            <img :src="topPic.picUrl" alt="">
            <div class="line4">
              <span class="iconfont icon-fangdajing"></span>
              <span>{{topPic.topicId}}人看过</span>
            </div>
            <div class="split_box"></div>
          </div>
        </li>
      </ul>
    </div>
  </div>
</template>
<script>
  import {mapGetters} from 'vuex'
  import BScroll from 'better-scroll'
  export default{
    mounted(){
      this.$store.dispatch('getKnowArtcile'),

          new BScroll('.recommend_box',{
            click:true
          })
    },
   computed:{
     ...mapGetters(['getTopPics']),
  }
  }
</script>
<style scoped lang="stylus" rel="stylesheet/stylus">
  .contentMessage
    width 100%
    min-height 1332px
    box-sizing border-box
    padding 162px 0 100px 0
    .recommend_box
      width 100%
      max-height 1070px
      overflow hidden
      box-sizing border-box
      padding-top 30px
      font-size 28px
      background-color #fff
      .left_right_box
        width 100%
        box-sizing border-box
        background-color white
        .wrapper
          display flex
          .left_box
            width 445px
            height 278px
            .line1
              width 100%
              margin 0 30px
              margin-bottom 20px
              font-size 28px
              img
                display inline-block
                width 40px
                height 40px
                margin-right 20px
                border-radius 50%
                vertical-align middle
            .line2
              margin-left 30px
              margin-bottom 15px
              font-size 36px
              color #333
              letter-spacing 2px
            .line3
              font-size 28px
              margin-bottom 30px
              color #7f7f7f
              margin-left 30px
            .line4
              margin 0 30px
              span
                font-size 24px
                color #999


          img
            width 278px
            height 278px
        .split_box
          height 20px
          margin 20px 0
          background-color #f4f4f4


      .line_show_box
        width 100%
        box-sizing border-box
        background-color #fff
        .line1
          width 100%
          margin 0 30px
          margin-bottom 20px
          font-size 28px
          img
            display inline-block
            width 40px
            height 40px
            margin-right 20px
            border-radius 50%
            vertical-align middle
        .line2
          margin-left 30px
          margin-bottom 15px
          font-size 36px
          color #333
          letter-spacing 2px
        img
          width 700px
          height 338px
          margin 0 30px
          margin-bottom 15px
        .line4
          margin 0 30px
          span
            font-size 24px
            color #999
      .split_box
        height 20px
        margin 20px 0
        background-color #f4f4f4
</style>
