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
  props: {
    recommendList: Array
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
