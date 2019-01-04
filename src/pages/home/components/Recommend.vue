<template>
  <div class="recommend">
    <div class="recommend-title">
      <img class="title-img" src="http://img1.qunarzz.com/piao/fusion/1711/89/ebc329f16c55bb02.png" alt="猜你喜欢">
      <span class="title-text">猜你喜欢</span>
    </div>
    <ul class="item-box">
      <li class="item border-bottom" v-for="item of recommendList" :key="item.id">
        <div class="item-img-box">
          <img class="item-img" :src="item.imgUrl">
        </div>
        <div class="item-info">
          <p class="item-title">{{item.title}}</p>
          <p class="item-comment">
            <span class="item-comment-star">
              <strong class="">★★★★★</strong>
            </span>
            <span>708条评论</span>
          </p>
          <button class="item-button">查看详情</button>
        </div>
      </li>
    </ul>
  </div>
</template>
<script>
export default {
  name: 'HomeRecommend',
  data () {
    return {
      recommendList: [{
        id: '0001',
        imgUrl: 'http://img1.qunarzz.com/sight/p0/201309/25/70edd368471094bdc8d65eac.jpg_200x200_75b6f391.jpg',
        title: '临安湍口众安氡温泉'
      }, {
        id: '0002',
        imgUrl: 'http://img1.qunarzz.com/sight/p0/1712/95/95f38f28a6ff19cba3.img.jpg_200x200_af967e35.jpg',
        title: '水奥雪世界'
      }, {
        id: '0003',
        imgUrl: 'http://img1.qunarzz.com/sight/p0/1511/d2/d2aec2dfc5aa771290.water.jpg_200x200_69e4a80d.jpg',
        title: '南山滑雪场'
      }, {
        id: '0004',
        imgUrl: 'http://img1.qunarzz.com/sight/p0/1411/43/dea8b51719a4a69b68777baa68c146e4.water.jpg_200x200_8da8cebe.jpg',
        title: '春晖园温泉度假村'
      }, {
        id: '0005',
        imgUrl: 'http://img1.qunarzz.com/sight/p0/1711/66/661d6a43e3e4dceda3.water.jpg_200x200_47eb3f51.jpg',
        title: '军都山滑雪场'
      }, {
        id: '0006',
        imgUrl: 'http://img1.qunarzz.com/sight/p0/1510/8e/8eea8eb6f41698290.img.jpg_200x200_595cfa1d.jpg',
        title: '金隅凤山温泉'
      }]
    }
  }
}
</script>
<style lang="stylus" scoped>
  @import '~styles/mixins.styl'
  .recommend-title
    padding: .24rem 0 .26rem;
    .title-img
      display: inline-block;
      overflow: hidden;
      width: .3rem;
      height: .3rem;
      margin-left: .2rem;
      vertical-align: top;
    .title-text
      display: inline-block;
      margin-left: .08rem;
      height: .44rem;
      color: #212121;
      font-size: .32rem;
      line-height: .44rem;
  .item-box
    margin-left: .24rem
    .item
      position: relative
      overflow: hidden
      padding: .2rem 0
      .item-img-box
        float: left
        overflow: hidden
        width: 2rem
        height: 2rem
        .item-img
          width: 100%
      .item-info
        overflow: hidden
        padding-left: .22rem
        .item-title
          margin-top: .26rem
          height: .44rem
          color: #212121
          font-size: .32rem
          line-height: .44rem
          ellipsis()
        .item-comment
          margin-top: .14rem
          height: .34rem
          font-size: .24rem
          color: #616161
          .item-comment-star
            width: 1.5rem
            height: .28rem
            line-height: .28rem
            font-size: .3rem
            letter-spacing: .02rem
            color: #ffb436
            margin-right: .2rem
        .item-button
          line-height: .44rem
          margin-top: .24rem
          background: #ff9300
          padding: .05rem .1rem
          border-radius: .06rem
          color: #fff
</style>
