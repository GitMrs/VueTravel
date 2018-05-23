<template>
  <div class="wrap">
    <swiper :options="swiperOption" ref="mySwiper" v-if="showSwiper">
      <swiper-slide v-for="item in swiperList" :key="item.id">
        <img :src="item.imgUrl" width="100%">
      </swiper-slide>
      <div class="swiper-pagination" slot="pagination"></div>
    </swiper>
  </div>
</template>
<script>
export default {
  props: {
    swiperList: Array
  },
  data () {
    return {
      swiperOption: {
        notNextTick: true,
        pagination: '.swiper-pagination',
        slidesPerView: 'auto',
        centeredSlides: true,
        paginationClickable: true,
        loop: true,
        autoplay: true,
        spaceBetween: 30
      }
    }
  },
  computed: {
    showSwiper () {
      return this.swiperList.length
    }
  }
}
</script>
<style lang="stylus" scoped>
  .wrap
    overflow : hidden
    width : 100%
    height : 0
    padding-bottom : 31.25%
    background : #eeeeee
</style>
