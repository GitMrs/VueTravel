<template>
    <div class="home">
        <homeHeader :city="city"></homeHeader>
        <homeSwiper :swiperList="SwiperList"></homeSwiper>
        <homeIcon :IconList="IconList"></homeIcon>
        <homeRecomend :RecomendList="RecomendList"></homeRecomend>
        <homeWeekend :WeekList="WeekList"></homeWeekend>
    </div>
</template>
<script>
import homeHeader from './components/homeHeader'
import homeSwiper from './components/swiper'
import homeIcon from './components/icon'
import homeRecomend from './components/recomend'
import homeWeekend from './components/weekend'
import axios from 'axios'
export default {
  name: 'home',
  components: {
    homeHeader,
    homeSwiper,
    homeIcon,
    homeRecomend,
    homeWeekend
  },
  data () {
    return {
      city: '',
      SwiperList: [],
      IconList: [],
      RecomendList: [],
      WeekList: []
    }
  },
  methods: {
    getHomeInfo () {
      axios.get('api/index.json').then(this.getHomeInfoSucc)
    },
    getHomeInfoSucc (res) {
      res = res.data
      if (res.ret && res.data) {
        const data = res.data
        this.city = data.city
        this.SwiperList = data.swiperList
        this.IconList = data.iconList
        this.RecomendList = data.recommendList
        this.WeekList = data.weekendList
        console.log(this.SwiperList)
      }
    }
  },
  mounted () {
    this.getHomeInfo()
  }
}
</script>
<style scoped>
</style>
