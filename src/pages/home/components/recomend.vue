<template>
    <div class="recomend-wrap">
        <div class="recommend-title">热销推荐</div>
        <ul>
          <router-link :to="'/detail/' + item.id" tag="li" class="item border-bottom" v-for="item of RecomendList" :key="item.id">
            <img class="item-img"  :src='item.imgUrl'>
            <div class="item-info">
                <p class="item-title">{{item.title}}</p>
                <p class="item-desc">{{item.desc}}</p>
                <button class="item-button">查看详情</button>
            </div>
          </router-link>
        </ul>
    </div>
</template>
<script>
export default {
  name: 'recomend',
  props: {
    RecomendList: Array
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
    .item
        overflow : hidden
        display : flex
        height : 1.9rem
        .item-img
            width : 1.7rem
            height : 1.7rem
            padding : .1rem
        .item-info
            flex : 1
            padding : .1rem
            .item-title
                line-height : .54rem
                font-size : .32rem
                ellipsis()
            .item-desc
                line-height : .4rem
                color : #cccccc
                ellipsis()
            .item-button
                background : #ff9300
                padding : 0 .2rem
                border-radius : .06rem
                margin-top : .2rem
                color : #fff
</style>
