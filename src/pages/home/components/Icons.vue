<template>
  <div class="icons">
    <swiper>
      <swiper-slide v-for="(page, index) of pages" :key="index">
        <div class="icon" v-for="item of page" :key="item.id">
          <div class="icon-box">
            <img class="icon-img" :src="item.iconUrl">
          </div>
          <p class="icon-text">{{item.iconText}}</p>
        </div>
      </swiper-slide>
    </swiper>
  </div>
</template>
<script>
export default {
  name: 'HomeIcons',
  data () {
    return {
      iconList: [{
        id: '0001',
        iconUrl: require('imgs/Icons/6f7d6e44963c9302.png'),
        iconText: '泡温泉'
      }, {
        id: '0002',
        iconUrl: require('imgs/Icons/13ceb38dcf262f02.png'),
        iconText: '一日游'
      }, {
        id: '0003',
        iconUrl: require('imgs/Icons/fdf170ee89594b02.png'),
        iconText: '杭州必游'
      }, {
        id: '0004',
        iconUrl: require('imgs/Icons/99402a22ce4af302.png'),
        iconText: '西湖'
      }, {
        id: '0005',
        iconUrl: require('imgs/Icons/e54fad3ea337b02.gif'),
        iconText: '年终大促'
      }, {
        id: '0006',
        iconUrl: require('imgs/Icons/eb88861d78fb9902.png'),
        iconText: '动植物园'
      }, {
        id: '0007',
        iconUrl: require('imgs/Icons/eca3ce656c886502.png'),
        iconText: '千岛湖'
      }, {
        id: '0008',
        iconUrl: require('imgs/Icons/f3dd6c383aeb3b02.png'),
        iconText: '景点门票'
      }, {
        id: '0009',
        iconUrl: require('imgs/Icons/c5dcdb58deec2402.png'),
        iconText: '西溪湿地'
      }, {
        id: '0010',
        iconUrl: require('imgs/Icons/8246f27355943202.png'),
        iconText: '游乐场'
      }]
    }
  },
  computed: {
    pages () {
      const pages = []
      this.iconList.forEach((item, index) => {
        const page = Math.floor(index / 8)
        if (!pages[page]) {
          pages[page] = []
        }
        pages[page].push(item)
      })
      return pages
    }
  }
}
</script>
<style lang="stylus" scoped>
  @import '~styles/varibles.styl'
  @import '~styles/mixins.styl'
  .icons >>> .swiper-container
    height: 0;
    padding-bottom: 50%;
  .icon
      position: relative;
      overflow: hidden;
      float: left;
      width: 25%;
      height: 0;
      padding-bottom: 25%;
      .icon-box
        position: absolute;
        top: 0;
        left: 0;
        right: 0;
        bottom: .44rem;
        box-sizing: border-box;
        padding: .1rem;
        .icon-img
          display: block;
          height: 100%;
          margin: 0 auto;
      .icon-text
        color: darkTextColor;
        position: absolute;
        left: 0;
        right: 0;
        bottom: 0;
        height: .44rem;
        line-height: .44rem;
        text-align: center;
        ellipsis()
</style>
