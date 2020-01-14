<template>
  <div>
    <div class="banner" @click="handleBannerClick">
      <img :src="bg">
      <div class="banner-info">
        <div class="banner-title">{{this.jd}}</div>
        <div class="banner-number"><span class="icon-uniE902"></span>39</div>
      </div>
    </div>
    <fade-ba>
      <common-gallary :imgs="swiper" v-show="showGallary" @close="handleGallaryClose"></common-gallary>
    </fade-ba>
  </div>
</template>

<script type="text/javascript">
import CommonGallary from 'common/gallary/Gallary'
import FadeBa from 'common/fade/FadeBa'
export default {
  name: 'DetailBanner',
  props: {
    bg: String,
    swiper: Array,
    jd: String
  },
  data () {
    return {
      showGallary: false
    }
  },
  methods: {
    handleBannerClick () {
      this.showGallary = true
    },
    handleGallaryClose () {
      this.showGallary = false
    }
  },
  components: {
    CommonGallary,
    FadeBa
  }
}
</script>

<style lang="stylus" scoped>
  .banner
    position: relative
    overflow: hidden
    height: 0
    padding-bottom: 55%
    .banner-img
      width: 100%
    .banner-info
      display: flex
      position: absolute
      left: 0
      right: 0
      bottom: 0
      line-height: .6rem
      color: #fff
      background: linear-gradient(top, rgba(0,0,0,0), rgba(0,0,0,.8))
      .banner-title
        flex: 1
        font-size: .32rem
      .banner-number
        margin-top: .14rem
        padding: 0 .4rem
        height: .32rem
        line-height: .32rem
        border-radius: .2rem
        background: rgba(0,0,0,.8)
        font-size: .24rem
        .banner-icon
          font-size: .24rem
</style>
