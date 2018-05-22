<template>
    <div class="home">
        <homeHeader></homeHeader>
        <homeSwiper></homeSwiper>
        <homeIcon></homeIcon>
    </div>
</template>
<script>
import homeHeader from './components/homeHeader'
import homeSwiper from './components/swiper'
import homeIcon from "./components/icon"
export default {
  components: {
    homeHeader,
    homeSwiper,
    homeIcon
  }
}
</script>
<style scoped>
</style>
