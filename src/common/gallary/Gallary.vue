<template>
    <div class="gallary" @click="handleGallaryClick">
        <div class="wraper">
            <swiper :options="swiperOption"  ref="mySwiper">
                <swiper-slide v-for="(item, index) in imgs" :key="index">
                    <img :src="item" width="100%">
                </swiper-slide>
                <div class="swiper-pagination" slot="pagination"></div>
            </swiper>
        </div>
    </div>
</template>
<script>
export default {
  name: 'gallary',
  props: {
    imgs: {
      type: Array,
      default () {
        return []
      }
    }
  },
  data () {
    return {
      swiperOption: {
        pagination: '.swiper-pagination',
        paginationType: 'fraction',
        observeParents: true,
        observer: true
      }
    }
  },
  methods: {
    handleGallaryClick () {
      this.$emit('close')
    }
  }
}
</script>
<style lang="stylus" scoped>
    .gallary
        display : flex
        justify-content : center
        flex-direction : column
        z-index : 99
        position : fixed
        left : 0
        top : 0
        bottom : 0
        width : 100%
        background : #000000
        .wraper
            width : 100%
            height : 0
            padding-bottom : 100%
            .swiper-pagination
                color : #fff
</style>
