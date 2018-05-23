<template>
    <div class="home">
        <homeHeader></homeHeader>
        <homeSwiper></homeSwiper>
        <homeIcon></homeIcon>
        <homeRecomend></homeRecomend>
        <homeWeekend></homeWeekend>
    </div>
</template>
<script>
import homeHeader from './components/homeHeader'
import homeSwiper from './components/swiper'
import homeIcon from './components/icon'
import homeRecomend from './components/recomend'
import homeWeekend from './components/weekend'
export default {
  components: {
    homeHeader,
    homeSwiper,
    homeIcon,
    homeRecomend,
    homeWeekend
  }
}
</script>
<style scoped>
</style>
