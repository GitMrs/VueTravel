<template>
    <div class="recomend-wrap">
        <div class="recommend-title">热销推荐</div>
        <ul>
            <li class="item border-bottom" v-for="item of recomendList" :key="item.id">
                <img class="item-img"  :src='item.imgUrl'>
                <div class="item-info">
                    <p class="item-title">{{item.title}}</p>
                    <p class="item-desc">{{item.desc}}</p>
                    <button class="item-button">查看详情</button>
                </div>
            </li>
        </ul>
    </div>
</template>
<script>
export default {
  name: 'recomend',
  data () {
    return {
      recomendList: [
        {
          id: '11221',
          imgUrl: 'http://img1.qunarzz.com/sight/p0/1409/19/adca619faaab0898245dc4ec482b5722.jpg_140x140_80f63803.jpg',
          title: '故宫',
          desc: '东方宫殿建筑代表，世界宫殿建筑典范'
        },
        {
          id: '11222',
          imgUrl: 'http://img1.qunarzz.com/sight/p0/1409/19/adca619faaab0898245dc4ec482b5722.jpg_140x140_80f63803.jpg',
          title: '故宫',
          desc: '东方宫殿建筑代表，世界宫殿建筑典范'
        },
        {
          id: '11223',
          imgUrl: 'http://img1.qunarzz.com/sight/p0/1409/19/adca619faaab0898245dc4ec482b5722.jpg_140x140_80f63803.jpg',
          title: '故宫',
          desc: '东方宫殿建筑代表，世界宫殿建筑典范'
        },
        {
          id: '11224',
          imgUrl: 'http://img1.qunarzz.com/sight/p0/1409/19/adca619faaab0898245dc4ec482b5722.jpg_140x140_80f63803.jpg',
          title: '故宫',
          desc: '东方宫殿建筑代表，世界宫殿建筑典范'
        },
        {
          id: '11225',
          imgUrl: 'http://img1.qunarzz.com/sight/p0/1409/19/adca619faaab0898245dc4ec482b5722.jpg_140x140_80f63803.jpg',
          title: '故宫',
          desc: '东方宫殿建筑代表，世界宫殿建筑典范'
        },
        {
          id: '11226',
          imgUrl: 'http://img1.qunarzz.com/sight/p0/1409/19/adca619faaab0898245dc4ec482b5722.jpg_140x140_80f63803.jpg',
          title: '故宫',
          desc: '东方宫殿建筑代表，世界宫殿建筑典范'
        }
      ]
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
