<template>
    <div class="citySearch">
        <input class="search-input" type="text" placeholder="输入城市名或拼音">
    </div>
</template>
<script>
export default {
  name: 'citySearch'
}
</script>
<style lang="stylus" scoped>
    @import '~styles/varbless.styl';
    .citySearch
        height : .72rem
        padding : 0 .1rem
        background : $bgColor
        .search-input
            width : 100%
            height : .62rem
            line-height : .6.2rem
            text-align : center
            border-radius : .06rem
            color : #666666
            box-sizing : border-box
            padding : 0 .1rem
</style>
