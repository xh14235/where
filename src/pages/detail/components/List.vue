<template>
  <div>
    <div class="list">
      <div class="item" v-for="(item, index) of list" :key="index">
        <div class="item-title">{{item.title}}</div>
        <div class="item-title2" v-if="item.children">
          <detail-list :list="item.children"></detail-list>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'DetailList',
  props: {
    list: Array
  }
}
</script>

<style lang="stylus" scoped>

</style>
