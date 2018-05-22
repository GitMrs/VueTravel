<template>
  <div class="wrap">
    <swiper :options="swiperOption" ref="mySwiper">
      <swiper-slide v-for="item in swiperList" :key="item.id">
        <img :src="item.imgUrl" width="100%">
      </swiper-slide>
      <div class="swiper-pagination" slot="pagination"></div>
    </swiper>
  </div>
</template>
<script>
export default {
  data () {
    return {
      swiperOption: {
        notNextTick: true,
        pagination: '.swiper-pagination',
        slidesPerView: 'auto',
        centeredSlides: true,
        paginationClickable: true,
        spaceBetween: 30
      },
      swiperList: [
        {
          id: '0001',
          imgUrl: 'http://img1.qunarzz.com/piao/fusion/1801/1a/94428c6dea109402.jpg_640x200_2cf590d8.jpg'
        },
        {
          id: '0002',
          imgUrl: 'http://img1.qunarzz.com/piao/fusion/1802/42/7c92b9a381e46402.jpg_640x200_1cdce2a4.jpg'
        },
        {
          id: '0003',
          imgUrl: 'http://img1.qunarzz.com/piao/fusion/1802/51/e78f936a5b404102.jpg_640x200_c14f0b3a.jpg'
        }
      ]
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
