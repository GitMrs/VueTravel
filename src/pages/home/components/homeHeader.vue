<template>
    <div class="header-wrap">
        <div class="header-left"><div class="iconfont back-icon">&#xe624;</div></div>
        <div class="header-input"><span class="iconfont">&#xe632;</span>请输入城市/景点/游玩主题</div>
        <router-link to="/city">
            <div class="header-right">{{this.$store.state.city}}<span class="iconfont arrow-icon">&#xe64a;</span></div>
        </router-link>
    </div>
</template>
<script>
export default {
  name: 'header-wrap'
}
</script>
<style lang="stylus" scoped>
  @import '~styles/varbless.styl'
    .header-wrap
        display : flex
        height: .86rem
        line-height : .86rem;
        background : #00bcd4
        color: #fff
        .header-left
            width: .64rem
            float: left
            .back-icon
                text-align : center
                font-size : .4rem
        .header-input
            flex : 1;
            height: .64rem
            line-height : .64rem
            margin-top : .12rem
            margin-left: .2rem
            background : #ffffff
            border-radius : .1rem
            color : #ccc
        .header-right
            min-width: 1.04rem
            padding : 0 .1rem
            float: right
            text-align : center
            color : #fff
            .arrow-icon
                margin-left : .1rem
                font-size : .24rem

</style>
