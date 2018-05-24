<template>
    <div class="cityDetial">
      <DetailHeader></DetailHeader>
      <DetailBanner :sightName="sightName" :bannerImg="bannerImg" :gallaryImgs="gallaryImgs"></DetailBanner>
      <div class="contain">
        <DetailList :categoryList="categoryList"></DetailList>
      </div>
    </div>
</template>
<script>
import DetailBanner from './components/DetailBanner'
import DetailHeader from './components/DetailHeader'
import DetailList from './components/DetailList'
import axios from 'axios'
export default {
  name: 'detail',
  data () {
    return {
      sightName: '',
      bannerImg: '',
      categoryList: [],
      gallaryImgs: []
    }
  },
  components: {
    DetailBanner,
    DetailHeader,
    DetailList
  },
  methods: {
    getInfo () {
      axios.get('/api/detail.json', {
        params: {
          id: this.$route.params.id
        }
      }).then(this.getData)
    },
    getData (res) {
      res = res.data
      if (res.ret && res.data) {
        const data = res.data
        this.sightName = data.sightName
        this.bannerImg = data.bannerImg
        this.categoryList = data.categoryList
        this.gallaryImgs = data.gallaryImgs
        console.log(data)
      }
    }
  },
  mounted () {
    this.getInfo()
  },
  activated () {
    this.getInfo()
  }
}
</script>
<style lang="stylus" scoped>
  .contain
    height : 1000px
    width : 100%
</style>
