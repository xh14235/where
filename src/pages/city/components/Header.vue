<template>
  <div class="header">
    <router-link to="/">
      <div class="icon-back"></div>
    </router-link>
    城市选择
  </div>
</template>

<script>
export default {
  name: 'CityHeader'
}
</script>

<style lang="stylus" scoped>
  @import '~styles/varibles.styl'
  .header
    position: relative
    height: $headerHeight
    line-height: $headerHeight
    text-align: center
    color: #fff
    font-size: .32rem
    background: $bgColor
    .icon-back
      position: absolute
      top: 0
      left: 0
      line-height: $headerHeight
      color: #fff
</style>
