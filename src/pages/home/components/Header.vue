<template>
  <div class="header">
    <div class="header-left">
      <div class="icon-back"></div>
    </div>
    <div class="header-input">
      <span class="icon-search"></span>
      输入经典主题
    </div>
    <router-link to="/city">
      <div class="header-right">
        {{this.city}}
        <span class="icon-uniE902"></span>
      </div>
    </router-link>
  </div>
</template>

<script>
import { mapState, mapGetters } from 'vuex'
export default {
  name: 'HomeHeader',
  computed: {
    ...mapState(['city']),
    ...mapGetters(['doubleCity'])
  }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/varibles.styl'
  .header
    display: flex
    line-height: $headerHeight
    background: $bgColor
    color: #fff
    .header-left
      width: .64rem
      float: left
      .icon-back
        text-align: center
        font-size: .4rem
        &:before
          line-height: $headerHeight
    .header-input
      flex: 1
      height: .64rem
      line-height: .64rem
      margin-left: .2rem
      padding-left: .2rem
      background: #fff
      margin-top: .12rem
      border-radius: .1rem
      color: #ccc
    .header-right
      min-width: 1.24rem
      padding: 0 .1rem
      float: right
      text-align: center
      color: #fff
</style>
