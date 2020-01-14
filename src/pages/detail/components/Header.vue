<template>
  <div>
    <router-link to="/">
      <div class="detail-back icon-back" v-show="showBack"></div>
    </router-link>
    <div class="detail-header" v-show="!showBack" :style="opcityStyle">
      <router-link tag="div" to="/" class="detail-back2 icon-back"></router-link>
      {{this.jd}}
    </div>
  </div>
</template>

<script>
export default {
  name: 'DetailHeader',
  props: {
    jd: String
  },
  data () {
    return {
      showBack: true,
      opcityStyle: 0
    }
  },
  methods: {
    handleScroll () {
      const top = document.documentElement.scrollTop
      if (top > 60) {
        let opacity = top / 140
        opacity = opacity > 1 ? 1 : opacity
        this.opcityStyle = { opacity }
        this.showBack = false
      } else {
        this.showBack = true
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
  @import '~styles/varibles.styl'
  .detail-back
    position: absolute
    top: .2rem
    left: .2rem
    width: .8rem
    height: .8rem
    line-height: .8rem
    text-align: center
    border-radius: 50%
    font-size: .4rem
    color: #fff
    background: rgba(0,0,0,.8)
  .detail-header
    z-index: 2
    position: fixed
    top: 0
    left: 0
    right: 0
    height: $headerHeight
    line-height: $headerHeight
    text-align: center
    color: #fff
    font-size: .32rem
    background: $bgColor
    .detail-back2
      position: absolute
      top: 0
      left: 0
      color: #fff
      line-height: $headerHeight
      font-size: .5rem
</style>
