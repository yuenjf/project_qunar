<template>
  <div>
    <div class="banner" @click="handleBannerClick">
      <img class="banner-img"
           :src="this.bannerImg" :alt="this.sightName">
      <div class="banner-info">
        <div class="banner-title">{{this.sightName}}</div>
        <div class="banner-number"><span class="iconfont banner-icon">&#xe6df;</span> {{this.gallaryImgs.length}}</div>
      </div>
    </div>
    <fade-animation>
      <common-gallary
        :imgs="this.gallaryImgs"
        v-show="showGallary"
        @close="handleGallaryClose"
      >
      </common-gallary>
    </fade-animation>
  </div>
</template>

<script>
  import CommonGallary from "common/gallary/Gallary"
  import FadeAnimation from "common/fade/FadeAnimation";

  export default {
    name: "DetailBanner",
    components: {
      CommonGallary,
      FadeAnimation
    },
    data() {
      return {
        showGallary: false,
      }
    },
    props: {
      sightName: String,
      bannerImg: String,
      gallaryImgs: Array
    },
    methods: {
      handleBannerClick() {
        this.showGallary = true
      },
      handleGallaryClose() {
        this.showGallary = false
      }
    },

  }
</script>

<style scoped lang="stylus">
  .banner
    position relative
    overflow hidden
    height 0
    padding-bottom 55%

    .banner-img
      width 100%

    .banner-info
      display flex
      position absolute
      left 0
      right 0
      bottom 0
      line-height .6rem
      color #fff
      /* 渐变 */
      background-image linear-gradient(top, rgba(0, 0, 0, 0), rgba(0, 0, 0, .8))

      .banner-title
        flex 1
        font-size .32rem
        padding 0 .2rem

      .banner-number
        height .32rem
        line-height .32rem
        margin-top .2rem
        padding 0 .4rem
        border-radius .2rem
        background rgba(0, 0, 0, .8)
        font-size .24rem

        .banner-icon
          font-size .24rem
</style>
