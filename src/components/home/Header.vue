<template>
  <div class="header">
    <div class="header-left">
      <span class="iconfont back-icon">&#xe7eb;</span>
    </div>
    <div class="header-input">
      <span class="iconfont">&#xe665;</span>
      输入城市景点/游玩/主题
    </div>
    <router-link to="/city">
      <div class="header-right">
        {{ this.city }}
        <span class="iconfont down-icon">&#xe6f0;</span>
      </div>
    </router-link>
  </div>
</template>

<script>
  import {mapState} from 'vuex'

  export default {
    name: "HomeHeader",
    computed: {
      ...mapState(['city'])
    }
  };
</script>

<style scoped lang="stylus">
  /* 样式中引入样式引入需要在import前加@符，路径前加~符 */
  @import '~styles/variables.styl'
  .header
    /* font-size = 50px - 1rem */
    display flex
    line-height $headerHeight
    background $bgColor
    color #fff

    .header-left
      width .64rem
      float left
      text-align center

      .back-icon
        font-size .4rem

    .header-input
      flex 1
      height .64rem
      line-height .64rem
      background #fff
      margin-top .12rem
      margin-left .2rem
      padding-left .2rem
      border-radius .1rem
      color #ccc

    .header-right
      min-width 1.04rem
      padding 0 .1rem
      float right
      text-align center
      color #fff

      .down-icon
        font-size .24rem
        margin-left -.04rem
</style>
