<template>
  <div class="weekend">
    <div class="title">周末去哪儿</div>
    <ul>
      <li class="item" v-for="item of list" :key="item.id">
        <div class="item-img-wrapper">
          <img class="item-img" :src="item.imgUrl" :alt="item.title" />
        </div>
        <div class="item-info border-bottom">
          <p class="item-title">{{ item.title }}</p>
          <p class="item-desc">{{ item.desc }}</p>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "HomeWeekend",
  props: {
    list: Array,
  },
};
</script>

<style scoped lang="stylus">
@import "~styles/mixins.styl"
.title
  margin-top .1rem
  line-height .8rem
  background #eee
  text-indent .2rem

.item-img-wrapper
  overflow hidden
  height 0
  padding-bottom 37.09%

  .item-img
    width 100%

.item-info
  flex 1
  padding .1rem
  min-width 0
  margin-bottom .24rem

  .item-title
    line-height .54rem
    font-size .32rem
    ellipsis()

  .item-desc
    line-height .4rem
    color #616161
    ellipsis()
</style>
