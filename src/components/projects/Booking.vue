<template>
  <div class="reservation-container border-bottom">
    <div
     class="reservation-item"
     v-for="(item, index) in list"
     :key="index"
    >
      <div class="reservation-left">
        <h6 class="left-title">
          {{item.title}}
        </h6>
        <div class="left-time">
          <img class="time-icon" src="https://img1.qunarzz.com/piao/fusion/1804/25/792e9929973a9902.png">
          {{item.time}}
        </div>
        <div class="left-info">
          <span class="info-item">
            <img class="info-icon" src="https://img1.qunarzz.com/piao/fusion/1804/b0/c3cf2897c74ecc02.png">
            {{item.self}}
          </span>
          <span class="info-item">
            {{item.refund}}
          </span>
        </div>
      </div>
      <div class="reservation-right">
        <div class="ticket-price">
          ￥{{item.price}}
        </div>
        <div class="ticket-button">预订</div>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  name: 'ReservationItem',
  props: {
    list: {
      type: Array,
      default () {
        return [{
          title: '（暖冬节）杭州云曼温泉成人票',
          time: '12：00前可订今日，预订后1小时可用',
          self: '自营',
          replace: '无需换票',
          refund: '条件退',
          price: 128
        }]
      }
    }
  }
}
</script>
<style lang="stylus" scoped>
  @import '~styles/mixins.styl'
  .reservation-item
    display: flex
    width: 100%
    .reservation-left
      color: #616161
      flex: 2.92
      align-items: center
      .left-title
        margin-right: .1rem
        line-height: .52rem
        padding: 0
        font-size: .3rem
        ellipsis2()
      .left-time
        display: inline-block
        height: .32rem
        line-height: .32rem
        font-size: .24rem
        white-space: nowrap;
        .time-icon
          display: inline-block
          width: .2rem
          max-height: .32rem
          margin-right: .04rem
          vertical-align: 0
      .left-info
        .info-item
          display: inline-block
          margin-top: .08rem
          margin-right: .1rem
          padding: 0 .04rem
          height: .32rem
          line-height: .32rem
          color: #00afc7
          font-size: .2rem
          white-space: nowrap
          border: 1px solid #a5e4ec
          transform-origin: 0 0
          border-radius: .08rem
          .info-icon
            display: inline-block
            width: .2rem
            max-height: .32rem
            margin-right: .04rem
            vertical-align: center
    .reservation-right
      width: 1.8rem
      .ticket-price
        overflow: hidden
        height: .4rem
        text-align: center
        color: #ff9800
        font-size: .4rem
      .ticket-button
        height: .6rem
        color: #fff
        font-size: .28rem
        line-height: .6rem
        text-align: center
        border-radius: .08rem
        background-image: linear-gradient(130deg,#ffab1e 37%,#ff8c12 100%)
</style>
