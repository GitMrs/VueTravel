<template>
    <div class="weekend-wrap">
        <div class="recommend-title">周末去哪</div>
        <ul>
            <li class="item border-bottom" v-for="item of recomendList" :key="item.id">
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
  data () {
    return {
      recomendList: [
        {
          id: '11221',
          imgUrl: 'http://img1.qunarzz.com/sight/source/1510/6e/1ea71e2f04e.jpg_r_640x214_aa6f091d.jpg',
          title: '故宫',
          desc: '东方宫殿建筑代表，世界宫殿建筑典范'
        },
        {
          id: '11222',
          imgUrl: 'http://img1.qunarzz.com/sight/source/1510/6e/1ea71e2f04e.jpg_r_640x214_aa6f091d.jpg',
          title: '故宫',
          desc: '东方宫殿建筑代表，世界宫殿建筑典范'
        },
        {
          id: '11223',
          imgUrl: 'http://img1.qunarzz.com/sight/source/1510/6e/1ea71e2f04e.jpg_r_640x214_aa6f091d.jpg',
          title: '故宫',
          desc: '东方宫殿建筑代表，世界宫殿建筑典范'
        },
        {
          id: '11224',
          imgUrl: 'http://img1.qunarzz.com/sight/source/1510/6e/1ea71e2f04e.jpg_r_640x214_aa6f091d.jpg',
          title: '故宫',
          desc: '东方宫殿建筑代表，世界宫殿建筑典范'
        },
        {
          id: '11225',
          imgUrl: 'http://img1.qunarzz.com/sight/source/1510/6e/1ea71e2f04e.jpg_r_640x214_aa6f091d.jpg',
          title: '故宫',
          desc: '东方宫殿建筑代表，世界宫殿建筑典范'
        },
        {
          id: '11226',
          imgUrl: 'http://img1.qunarzz.com/sight/source/1510/6e/1ea71e2f04e.jpg_r_640x214_aa6f091d.jpg',
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
