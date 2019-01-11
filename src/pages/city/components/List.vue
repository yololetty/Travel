<template>
  <div class="list" ref="wrapper">
    <div>
      <div class="area">
        <div class="title border-topbottom">热门城市</div>
        <div class="button-list">
          <div
            class="button-wrapper"
            v-for="item of hot"
            :key="item.id"
            @click="handleCityClick(item.name)"
          >
            <div class="button">{{item.name}}</div>
          </div>
        </div>
      </div>
      <div
        class="area"
        v-for="(item, key) of cities"
        :key="key"
         :ref="key"
      >
        <div class="title border-topbottom">{{key}}</div>
        <div class="list-wrapper">
          <div
            class="item-list"
            v-for="innerItem of item"
            :key="innerItem.id"
            @click="handleCityClick(innerItem.name)"
          >
            <div class="item">{{innerItem.name}}</div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
import Bscroll from 'better-scroll'
import {mapMutations} from 'vuex'
export default {
  name: 'CityList',
  props: {
    cities: Object,
    hot: Array,
    letter: String
  },
  methods: {
    handleCityClick (city) {
      this.changeCity(city)
      this.$router.push('/')
    },
    ...mapMutations(['changeCity'])
  },
  watch: {
    letter () {
      if (this.letter) {
        const element = this.$refs[this.letter][0]
        this.scroll.scrollToElement(element)
      }
    }
  },
  mounted () {
    this.scroll = new Bscroll(this.$refs.wrapper)
  }
}
</script>
<style lang="stylus" scoped>
  @import '~styles/mixins.styl'
  .list
    overflow: hidden
    position: absolute
    top: 1.58rem
    left: 0
    right: 0
    bottom: 0
    .title
      height: .66rem
      line-height: .66rem
      background: #F5F5F5
      color: #212121
      padding-left: .2rem
      font-size: .24rem
    .border-topbottom
      $:before
        border-color: #ccc
      $:after
        border-color: #ccc
    .button-list
      overflow: hidden
      position: relative
      .button-wrapper
        float: left
        width: 33.33%
        height: .9rem
        line-height: .9rem
        text-align: center
        border-bottom: .02rem solid #ddd
        ellipsis()
    .button-list:before
      position: absolute
      z-index: -1
      content: '';
      height: 100%
      width: 33.33%
      left: 33.33%
      border-left: .02rem solid #ddd
      border-right: .02rem solid #ddd
    .list-wrapper
      position: relative
      overflow: hidden
      .item
        width: 25%
        height: .9rem
        line-height: .9rem
        text-align: center
        border-bottom: .02rem solid #ddd
        float: left
        position: relative
        ellipsis()
    .list-wrapper:before
      content: ''
      position: absolute
      width: 25%
      height: 100%
      left: 25%
      border-left: .02rem solid #ddd
      border-right: .02rem solid #ddd
    .list-wrapper:after
        content: '';
        position: absolute;
        width: 10%;
        left: 75%;
        height: 100%;
        border-left: .02rem solid #ddd;
        border-right: 0;
</style>
