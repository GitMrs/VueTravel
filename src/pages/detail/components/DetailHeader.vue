<template>
    <div>
        <router-link v-show="showAbs" to="/" tag="div" class="header-abs">
            <div class="iconfont back-icon">&#xe624;</div>
        </router-link>
        <div class="header-fixd" v-show="!showAbs" :style="opacityStyle">
            <router-link to="/">
                <div class="iconfont header-back">&#xe624;</div>
            </router-link>
            景点详情
        </div>
    </div>
</template>
<script>
export default {
  name: 'detailHeader',
  data () {
    return {
      showAbs: true,
      opacityStyle: {
        opacity: 0
      }
    }
  },
  methods: {
    handleScroll () {
      console.log('111')
      const top = document.documentElement.scrollTop
      if (top > 60) {
        let opacity = top / 140
        opacity = opacity > 1 ? 1 : opacity
        this.opacityStyle = { opacity }
        this.showAbs = false
      } else {
        this.showAbs = true
      }
    }
  },
  activated () {
    console.log(11)
    window.addEventListener('scroll', this.handleScroll)
  },
  deactivated () {
    window.removeEventListener('scroll', this.handleScroll)
  }
}
</script>
<style lang="stylus" scoped>
    @import '~styles/varbless.styl';
    .header-abs
        position : absolute
        left : .2rem
        top : .2rem
        width : .8rem
        height : .8rem
        border-radius : .4rem
        background : #333
        z-index : 100
        text-align : center
        line-height : .8rem
        .back-icon
            font-size : .4rem
            color : #fff
    .header-fixd
        position : fixed
        top : 0
        left : 0
        right : 0
        overflow : hidden
        height : .86rem
        z-index : 10000
        line-height : .86rem
        text-align : center
        color : #ffffff
        font-size : .32rem
        background : $bgColor
        .header-back
            position : absolute
            left : 0
            top : 0
            width : .64rem
            color : #fff
            text-align : center
            font-size : .4rem
</style>
