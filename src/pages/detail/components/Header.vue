<template>
  <div>
    <router-link
      tag="div"
      to="/"
      class="header-abs"
      v-show="showAbs"
    >
      <div class="iconfont header-abs-back">&#xe624;</div>
    </router-link>
    <div
      class="header-fixed"
      v-show="!showAbs"
      :style="opacityStyle"
    >
      <default-header
        :title="title"
      ></default-header>
    </div>
  </div>
</template>
<script>
import DefaultHeader from 'projects/Header'
export default {
  name: 'DetailHeader',
  components: {
    DefaultHeader
  },
  data () {
    return {
      title: '景点详情',
      showAbs: true,
      opacityStyle: {
        opacity: 0
      }
    }
  },
  methods: {
    handleScroll () {
      const top = document.documentElement.scrollTop
      console.log(top)
      if (top > 60) {
        let opacity = top / 140
        opacity = opacity > 1 ? 1 : opacity
        this.opacityStyle = {
          opacity
        }
        this.showAbs = false
      } else {
        this.showAbs = true
      }
    }
  },
  activated () {
    window.addEventListener('scroll', this.handleScroll)
  },
  deactivated () {
    window.removeEventListener('scroll', this.handleScroll)
  }
}
</script>
<style lang="stylus" scoped>
  .header-abs
    position: absolute
    top: .2rem
    left: .2rem
    width: .72rem
    height: .72rem
    line-height: .8rem
    border-radius: .36rem
    text-align: center
    background: rgba(0, 0, 0, .6)
    .header-abs-back
      color: #fff
      font-size: .4rem
  .header-fixed
    z-index: 2
    position: fixed
    top: 0
    left: 0
    right: 0
</style>
