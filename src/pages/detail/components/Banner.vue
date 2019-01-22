<template>
  <div>
    <div class="banner" @click="handleGallary">
      <div class="img-wrap">
        <img class="banner-img" src="//img1.qunarzz.com/sight/p0/1810/cc/cc47164357acbeb5a3.water.jpg_600x330_aed5d0a5.jpg">
      </div>
      <div class="banner-info">
        <div class="banner-icon">
          <span class="iconfont">&#xe60e;</span>
          14
        </div>
        <div class="banner-title">杭州云曼温泉</div>
      </div>
    </div>
    <common-gallary
      :imgs="imgs"
      v-show="showGallary"
      @close="closeGallary"
    ></common-gallary>
  </div>
</template>
<script>
import CommonGallary from 'common/gallary/Gallary'
export default {
  name: 'DetailBanner',
  data () {
    return {
      showGallary: false,
      imgs: ['http://img1.qunarzz.com/sight/p0/1810/cc/cc47164357acbeb5a3.water.jpg_r_800x800_0271f7e2.jpg',
        'http://img1.qunarzz.com/sight/p0/1810/32/32392eea822d11c8a3.water.jpg_r_800x800_4172a5f9.jpg']
    }
  },
  components: {
    CommonGallary
  },
  methods: {
    handleGallary () {
      this.showGallary = true
    },
    closeGallary () {
      this.showGallary = false
    }
  }
}
</script>
<style lang="stylus" scoped>
  .banner
    position: relative
    .img-wrap
      overflow: hidden
      height: 0
      width: 100%
      padding-bottom: 55%
      .banner-img
        width: 100%
        vertical-align: top
    .banner-info
      position: absolute
      left: .2rem
      right: .2rem
      bottom: .36rem
      color: #fff
      .banner-icon
        width: 1.2rem
        height: .4rem
        line-height: .4rem
        margin-bottom: .15rem
        font-size: .24rem
        border-radius: .2rem
        text-align: center
        background: rgba(0, 0, 0, .5)
        .iconfont
          font-size: 12px
      .banner-title
        font-size: .36rem
        text-shadow: 0 1px 2px rgba(0, 0, 0, .7)
  .banner::after
    content: ''
    display: block
    position: absolute
    bottom: 0
    left: 0
    width: 100%
    min-height: .6rem
    background-color: transparent
    background-image: linear-gradient(top, rgba(0, 0, 0, 0), rgba(0, 0, 0, 0.8))
</style>
