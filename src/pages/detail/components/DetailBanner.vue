<template>
    <div>
        <div @click="handleBannerClick" class="banner">
            <img :src="bannerImg" class="banner-img" alt="">
            <div class="banner-info">
                <div class="banner-title">
                    {{this.sightName}}
                </div>
                <div class="banner-num">
                    <span class="icon-num iconfont">&#xe692;</span>
                    {{this.gallaryImgs.length}}
                </div>
            </div>
        </div>
        <Fade>
            <common-gallary @close="handleClose" v-show="showGallary" :imgs="gallaryImgs"></common-gallary>
        </Fade>
    </div>
</template>
<script>
import CommonGallary from 'common/gallary/Gallary'
import Fade from 'common/fade/fade'
export default {
  name: 'detailBanner',
  props: {
    sightName: String,
    bannerImg: String,
    gallaryImgs: Array
  },
  data () {
    return {
      imgs: [],
      showGallary: false
    }
  },
  components: {
    CommonGallary,
    Fade
  },
  methods: {
    handleBannerClick () {
      this.showGallary = true
    },
    handleClose () {
      this.showGallary = false
    }
  }
}
</script>
<style lang="stylus" scoped>
    .banner
        overflow : hidden
        height : 0
        padding-bottom : 55%
        position : relative
        .banner-img
            width : 100%
        .banner-info
            display : flex
            position : absolute
            left : 0
            right : 0
            bottom : 0
            line-height : .6rem
            color: #ffffff
            background-image : linear-gradient(top, rgba(0, 0, 0, 0), rgba(0, 0, 0, .8))
            .banner-title
                flex :1
                font-size : .32rem
                padding : 0 .2rem
            .banner-num
                padding : 0 .4rem
                line-height : .32rem
                height : .32rem
                margin-top : .16rem
                border-radius : .2rem
                font-size : .24rem
                background :rgba(0,0,0,.4)
                .icon-num
                    font-size : .24rem

</style>
