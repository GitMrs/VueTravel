<template>
    <div class="header">
        城市选择
        <router-link to="/">
            <div class="iconfont header-back">&#xe624;</div>
        </router-link>
    </div>
</template>
<script>
export default {
  name: 'CityHeader'
}
</script>
<style lang="stylus" scoped>
  @import '~styles/varbless.styl'
    .header
        overflow : hidden
        height : .86rem
        line-height : .86rem
        text-align : center
        color : #ffffff
        font-size : .32rem
        background : $bgColor
        position : relative
        .header-back
            position : absolute
            left : 0
            top : 0
            width : .64rem
            color : #fff
            text-align : center
            font-size : .4rem
</style>
