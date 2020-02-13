<template>
  <div class="list">
    <div class="recommend-container">
      <div class="ticket-group">
        <h3 class="group-title border-bottom">
          <span class="title-icon">
            <i class="iconfont up-icon">&#xe600;</i>
          </span>
          去哪儿推荐
        </h3>
        <booking-item
          class="group-item"
          :list="list1"></booking-item>
      </div>
    </div>
  </div>
</template>
<script>
import BookingItem from 'projects/Booking'
export default {
  name: 'DetailList',
  components: {
    BookingItem
  },
  data () {
    return {
      list1: [{
        title: '【2.5--2.10】云曼温泉直销成人票',
        time: '可订2月5日',
        self: '自营',
        replace: '无需换票',
        refund: '条件退',
        price: 138
      }]
    }
  }
}
</script>
<style lang="stylus" scoped>
  .ticket-group
    position: relative
    background: #fff
    margin-bottom: .2rem
    padding-left: .2rem
    .group-title
      overflow: hidden
      position: relative
      margin-bottom: -.02rem
      height: .88rem
      background: #fff
      color: #333
      font-size: .32rem
      line-height: .88rem
      .title-icon
        display: inline-block
        width: .4rem
        height: .4rem
        line-height : .4rem
        border-radius: .2rem
        background: #FF6E6E
        color: #fff
        text-align: center
        margin-right: .15rem
        .up-icon
          font-size: .3rem
    .group-item
      padding: .2rem .2rem .24rem 0
  .ticket-container
    .t-group-title
      overflow: hidden
      position: relative
      z-index: 4
      margin-bottom: -.02rem
      padding: 0 .2rem
      height: .88rem
      background: #fff
      color: #333
      font-size: .32rem
      line-height: .88rem
      text-indent: .4rem
      .t-title-icon
        width: .36rem;
        height: .36rem;
        top: .26rem;
        left: .2rem;
        background: url(//s.qunarzz.com/piao/image/touch/sight/detail.png) 0 -.45rem no-repeat;
        margin-right: .1rem;
        background-size: .4rem 3rem;
</style>
