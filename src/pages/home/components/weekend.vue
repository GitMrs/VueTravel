<template>
    <div class="weekend-wrap">
        <div class="recommend-title">周末去哪</div>
        <ul>
            <li class="item border-bottom" v-for="item of WeekList" :key="item.id">
                <div class="item-img-wrap">
                    <img class="item-img"  :src='item.imgUrl'>
                </div>
                <div class="item-info">
                    <p class="item-title">{{item.title}}</p>
                    <p class="item-desc">{{item.desc}}</p>
                </div>
            </li>
        </ul>
    </div>
</template>
<script>
export default {
  name: 'recomend',
  props: {
    WeekList: Array
  },
  data () {
    return {
    }
  }
}
</script>
<style lang="stylus" scoped>
    @import '~styles/mixins.styl';
    .recommend-title
        line-height : .8rem
        background : #eeeeee
        text-align : center
        margin-top : .2rem
    .item-img-wrap
        overflow : hidden
        height : 0
        padding-bottom : 33.9%
    .item-img
        width : 100%
    .item-info
        padding : .1rem
        .item-title
            line-height : .54rem
            font-size : .32rem
            ellipsis()
        .item-desc
            line-height : .4rem
            color : #cccccc
            ellipsis()
</style>
