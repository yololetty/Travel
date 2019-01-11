<template>
  <div class="weekend">
    <h2 class="weekend-title">周末去哪儿</h2>
    <ul class="item-box">
      <li class="item" v-for="item of weekendList" :key="item.id">
        <img class="item-img" :src="item.imgUrl">
        <div class="item-info">
          <p class="item-title">{{item.title}}</p>
          <p class="item-desc">{{item.desc}}</p>
        </div>
      </li>
    </ul>
  </div>
</template>
<script>
export default {
  name: 'HomeWeekend',
  props: {
    weekendList: Array
  }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/mixins.styl'
  @import '~styles/varibles.styl'
  .weekend-title
    height: .8rem
    padding-left: .26rem
    line-height: .8rem
    color: titleColor
    background: #f5f5f5
  .item
    position: relative
    overflow: hidden
    margin-bottom: .1rem
    .item-img
      overflow: hidden
      width: 100%
    .item-info
      padding: .14rem .2rem .2rem
      .item-title
        padding-right: 1.4rem
        color: titleColor
        font-size: .28rem
        line-height: .48rem
        ellipsis()
      .item-desc
        padding-right: 1.4rem
        line-height: .42rem
        font-size: .24rem
        color: #616161
        ellipsis()
</style>
