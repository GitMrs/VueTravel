<template>
    <div class="citySearch">
        <input v-model="keyworld" class="search-input" type="text" placeholder="输入城市名或拼音">
        <div class="search-content" ref="search" v-show="keyworld">
            <ul>
                <li class="search-item border-bottom"  @click="handleClick(item)" v-for="item of list" :key="item.id">{{item}}</li>
                <li class="search-item border-bottom" v-show="hasNoData" >没有找到匹配数据</li>
            </ul>
        </div>
    </div>
</template>
<script>
import Bscroll from 'better-scroll'
export default {
  name: 'citySearch',
  props: {
    cities: Object
  },
  data () {
    return {
      keyworld: '',
      list: [],
      timer: null
    }
  },
  watch: {
    keyworld () {
      if (this.timer) {
        clearTimeout(this.timer)
      }
      if (!this.keyworld) {
        this.list = []
        return false
      }
      this.timer = setTimeout(() => {
        const result = []
        for (let i in this.cities) {
          this.cities[i].forEach((item) => {
            if (item.spell.indexOf(this.keyworld) > -1 || item.name.indexOf(this.keyworld) > -1) {
              result.push(item.name)
            }
          })
        }
        this.list = result
      }, 100)
    }
  },
  mounted () {
    this.scroll = new Bscroll(this.$refs.search)
  },
  computed: {
    hasNoData () {
      return !this.list.length
    }
  },
  methods: {
    handleClick (city) {
      this.$store.commit('changeCity', city)
      this.$router.push('/')
    }
  }
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
        .search-content
            position : absolute
            overflow : hidden
            top : 1.58rem
            left: 0
            right : 0
            bottom : 0
            background : #eee
            z-index : 1
            .search-item
              line-height : .62rem
              padding-left : .2rem
              color : #666
              background : #fff
</style>
