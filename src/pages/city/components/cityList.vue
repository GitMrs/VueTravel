<template>
    <div class="list" ref="wrapper">
        <div>
            <div class="area">
                <div class="title border-topbottom">当前城市</div>
                <div class="button-list">
                    <div class="button-wrap">
                        <div class="button">{{this.$store.state.city}}</div>
                    </div>
                </div>
            </div>
            <div class="area">
                <div class="title border-topbottom">热门城市</div>
                <div class="button-list">
                    <div class="button-wrap" @click="handleClick(item.name)" v-for="item of list" :key="item.id">
                        <div class="button">{{item.name}}</div>
                    </div>
                </div>
            </div>
            <div class="area" v-for="(item, key) of cities" :ref="key" :key="key">
                <div class="title border-topbottom">{{key}}</div>
                <div class="item-list" @click="handleClick(city.name)" v-for="(city, index) of item" :key="index" >
                    <div class="item border-bottom">{{city.name}}</div>
                </div>
            </div>
        </div>
    </div>
</template>
<script>
import Bscroll from 'better-scroll'
export default {
  name: 'cityList',
  props: {
    list: Array,
    cities: Object,
    Leter: String
  },
  mounted () {
    this.scroll = new Bscroll(this.$refs.wrapper)
  },
  methods: {
    handleClick (city) {
      this.$store.dispatch('changeCity', city)
      this.$router.push('/')
    }
  },
  watch: {
    Leter () {
      if (this.Leter) {
        const element = this.$refs[this.Leter][0]
        this.scroll.scrollToElement(element)
      }
    }
  }
}
</script>
<style lang="stylus" scoped>
    .border-topbottom
        &:before
            border-color : #ccc
        &:after
            border-color : #ccc
    .border-bottom
        &:before
            border-color : #ccc
    .list
        overflow : hidden
        position : absolute
        top : 1.58rem
        left : 0
        bottom : 0
        right : 0
        .title
            line-height : .54rem
            background : #eeeeee
            padding-left : .2rem
            color : #666666
        .button-list
            padding : .1rem .6rem .1rem .1rem
            overflow : hidden
            .button-wrap
                float : left
                width : 33.33%
                .button
                    padding : .1rem 0
                    text-align : center
                    margin : .1rem .1rem
                    border : .02rem solid #ccc;
                    border-radius : .06rem
        .item-list
            .item
                line-height : .76rem
                padding-left : .2rem
</style>
