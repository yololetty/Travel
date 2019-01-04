<template>
  <div class="hotlist">
    <div class="list-title-box">
      <img class="list-title-img" src="http://img1.qunarzz.com/piao/fusion/1711/16/bfbb9874e8f11402.png" alt="本周热门榜单">
      <span class="list-title">本周热门榜单</span>
      <a class="list-title-more" href="#">全部榜单 ></a>
    </div>
    <ul class="hotsale-list">
      <li class="hotsale-item" v-for="item of hotList" :key="item.id">
        <img class="hotsale-tagimg"  src="http://img1.qunarzz.com/piao/fusion/1710/ab/159673b63e6ca702.png">
        <img class="hotsale-imgcon" :src="item.imgUrl">
        <div class="hotsale-sight">{{item.sight}}</div>
        <div class="hotsale-price">{{item.price}}</div>
      </li>
    </ul>
  </div>
</template>
<script>
export default {
  name: 'HomeHotlist',
  data () {
    return {
      hotList: [{
        id: '0001',
        imgUrl: 'http://img1.qunarzz.com/sight/p0/1409/19/adca619faaab0898245dc4ec482b5722.jpg_250x250_0fc722c0.jpg',
        sight: '故宫',
        price: '￥20'
      }, {
        id: '0002',
        imgUrl: 'http://img1.qunarzz.com/sight/p0/1712/71/71ace1aa7d971212a3.water.jpg_250x250_f35a11db.jpg',
        sight: '故宫',
        price: '￥20'
      }, {
        id: '0003',
        imgUrl: 'http://img1.qunarzz.com/sight/p0/1511/d2/d2aec2dfc5aa771290.water.jpg_250x250_7b67daa3.jpg',
        sight: '故宫',
        price: '￥20'
      }, {
        id: '0004',
        imgUrl: 'http://img1.qunarzz.com/sight/p0/1712/71/71ace1aa7d971212a3.water.jpg_250x250_f35a11db.jpg',
        sight: '故宫',
        price: '￥20'
      }, {
        id: '0005',
        imgUrl: 'http://img1.qunarzz.com/sight/p0/1511/d2/d2aec2dfc5aa771290.water.jpg_250x250_7b67daa3.jpg',
        sight: '故宫',
        price: '￥20'
      }]
    }
  }
}
</script>
<style lang="stylus" scoped>
  @import '~styles/varibles.styl'
  @import '~styles/mixins.styl'
  .hotlist
    margin-top: .2rem
    .list-title-box
      position: relative
      padding: .24rem 0 .26rem
      .list-title-img
        display: inline-block
        overflow: hidden
        width: .3rem
        height: .3rem
        margin-left: .2rem
        vertical-align: top
      .list-title
        display: inline-block
        margin-left: .08rem
        height: .44rem
        color: titleColor
        font-size: .32rem
        line-height: .44rem
      .list-title-more
        position: absolute
        top: .36rem
        right: .32rem
        color: #616161
        font-size: .24rem
        line-height: .28rem
    .hotsale-list
      padding: 0 .24rem
      overflow-x: scroll
      white-space: nowrap
      .hotsale-item
        position: relative
        display: inline-block
        padding: .06rem 0 .2rem
        width: 2rem
        margin-right: .12rem
        .hotsale-tagimg
          position: absolute
          top: 0
          left: 0
          z-index: 1
          overflow: hidden
          width: .84rem
          height: .4rem
        .hotsale-imgcon
          overflow: hidden
          width: 2rem
          height: 2rem
        .hotsale-sight
          margin-top: .12rem
          color: titleColor
          font-size: .24rem
          line-height: .32rem
          text-align: center
          ellipsis()
        .hotsale-price
          color: #ff8300
          font-size: .28rem
          line-height: .36rem
          text-align: center
</style>
