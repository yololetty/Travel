<template>
  <div class="wrapper">
    <swiper :options="swiperOption">
      <!-- slides -->
      <swiper-slide v-for="item of swiperList" :key="item.id">
        <img class="swiper-img" :src="item.imgUrl">
      </swiper-slide>
      <!-- Optional controls -->
      <div class="swiper-pagination"  slot="pagination"></div>
    </swiper>
  </div>
</template>

<script>
export default {
  name: 'HomeSwiper',
  data () {
    return {
      swiperOption: {
        pagination: '.swiper-pagination',
        loop: true
      },
      swiperList: [{
        id: '0001',
        imgUrl: require('imgs/6b1f0402bb1d5902.jpg')
      }, {
        id: '0002',
        imgUrl: require('imgs/8e5c4ab8ee8b7402.jpg')
      }, {
        id: '0003',
        imgUrl: require('imgs/30ffcf34e9819f02.jpg')
      }, {
        id: '0004',
        imgUrl: require('imgs/72ce947f4dff4c02.jpg')
      }, {
        id: '0005',
        imgUrl: require('imgs/5713e2a2ba72f902.jpg')
      }, {
        id: '0006',
        imgUrl: require('imgs/806541e769362f02.jpg')
      }, {
        id: '0007',
        imgUrl: require('imgs/a51fe403715df102.jpg')
      }]
    }
  }
}
</script>

<style lang="stylus" scoped>
  .wrapper >>> .swiper-pagination-bullet-active
    background: #fff
  .wrapper
    overflow: hidden
    width: 100%
    height: 0
    padding-bottom: 26.67%
    background: #eee
    .swiper-img
      width: 100%
</style>
