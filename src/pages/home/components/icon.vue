<template>
    <div class="index-icon-wrap">
        <swiper  :options="swiperOption">
            <swiper-slide v-for="(page, index) of pages" :key="index">
                <div class="icon" v-for="(item, index) in page" :key="index">
                <div class="icon-img">
                    <img class="icon-img-content" :src="item.imgUrl" height="100%">
                </div>
                    <p>{{item.desc}}</p>
                </div>
            </swiper-slide>
        </swiper>
    </div>
</template>
<script>
export default {
  name: 'index-icon',
  props: {
    IconList: Array
  },
  data () {
    return {
      swiperOption: {
        autoplay: false
      }
    }
  },
  computed: {
    pages () {
      const pages = []
      this.IconList.forEach((item, index) => {
        const page = Math.floor(index / 8)
        if (!pages[page]) {
          pages[page] = []
        }
        pages[page].push(item)
      })
      return pages
    }
  }
}
</script>
<style lang="stylus" scoped>
.index-icon-wrap {
    height: 0;
    overflow: hidden;
    padding-bottom: 50%;
    margin-top : .1rem;
    .icon {
        float: left;
        height: 0;
        width: 25%;
        padding-bottom: 25%;
        position: relative;

        .icon-img {
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0.44rem;
            box-sizing: border-box;
            padding: 0.1rem;

            .icon-img-content {
                height: 100%;
                display: block;
                margin: 0 auto;
            }
        }

        p {
            text-align: center;
            position: absolute;
            line-height: 0.44rem;
            color: #333;
            bottom: 0;
            width: 100%;
        }
    }
}
</style>
