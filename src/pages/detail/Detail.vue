<template>
  <div>
    <detail-banner :bg="this.bgImg" :swiper="swiperImg" :jd="jdTitle"></detail-banner>
    <detail-header :jd="jdTitle"></detail-header>
    <detail-list :list="list" style="height: 50rem"></detail-list>
  </div>
</template>

<script>
import DetailBanner from './components/Banner'
import DetailHeader from './components/Header'
import DetailList from './components/List'
import axios from 'axios'
export default {
  name: 'Detail',
  components: {
    DetailBanner,
    DetailHeader,
    DetailList
  },
  data () {
    return {
      list: [],
      bgImg: '',
      swiperImg: [],
      jdTitle: ''
    }
  },
  methods: {
    getDetailInfo () {
      axios.get('/api/detail.json', {
        params: {
          id: this.$route.params.id
        }
      }).then(this.getDetailInfoSucc)
    },
    getDetailInfoSucc (res) {
      const resu = res.data
      if (resu.ret && resu.data) {
        const data = resu.data
        this.list = data.categoryList
        this.bgImg = data.bannerImg
        this.swiperImg = data.gallaryImgs
        this.jdTitle = data.sightName
      }
    }
  },
  mounted () {
    this.getDetailInfo()
  }
}
</script>

<style>

</style>
