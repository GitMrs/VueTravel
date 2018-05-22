<template>
    <div class="index-icon-wrap">
        <swiper>
            <swiper-slide v-for="(page, index) of pages" :key="index">
                <div class="icon" v-for="item in page" :key="item.id">
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
    data () {
        return {
            iconList: [
                {
                    id: '0001',
                    imgUrl: 'http://img1.qunarzz.com/piao/fusion/1611/54/ace00878a52d9702.png',
                    desc: '景点门票'
                },
                {
                    id: '0002',
                    imgUrl: 'http://img1.qunarzz.com/piao/fusion/1711/df/86cbcfc533330d02.png',
                    desc: '滑雪季'
                },
                {
                    id: '0003',
                    imgUrl: 'http://img1.qunarzz.com/piao/fusion/1710/a6/83f636bd75ae6302.png',
                    desc: '泡温泉'
                },
                {
                    id: '0004',
                    imgUrl: 'http://img1.qunarzz.com/piao/fusion/1611/35/2640cab202c41b02.png',
                    desc: '植物园'
                },
                  {
                    id: '0001',
                    imgUrl: 'http://img1.qunarzz.com/piao/fusion/1611/54/ace00878a52d9702.png',
                    desc: '景点门票'
                },
                {
                    id: '0002',
                    imgUrl: 'http://img1.qunarzz.com/piao/fusion/1711/df/86cbcfc533330d02.png',
                    desc: '滑雪季'
                },
                {
                    id: '0003',
                    imgUrl: 'http://img1.qunarzz.com/piao/fusion/1710/a6/83f636bd75ae6302.png',
                    desc: '泡温泉'
                },
                {
                    id: '0004',
                    imgUrl: 'http://img1.qunarzz.com/piao/fusion/1611/35/2640cab202c41b02.png',
                    desc: '植物园'
                },
                {
                    id: '0005',
                    imgUrl: 'http://img1.qunarzz.com/piao/fusion/1611/d0/e09575e66f4aa402.png',
                    desc: '一日游'
                }
            ]
        }
    },
    computed: {
        pages () {
            const pages = []
            this.iconList.forEach((item, index)=>{
                const page = Math.floor(index/8)
                if(!pages[page]) {
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
    .index-icon-wrap
        height : 0
        overflow : hidden
        padding-bottom : 50%
        .icon
            float : left
            height : 0
            width : 25%
            padding-bottom : 25%
            position : relative
            .icon-img
                position : absolute
                top : 0
                left :0
                right :0
                bottom :.44rem
                box-sizing : border-box
                padding : .1rem
                .icon-img-content{
                    height : 100%
                    display : block
                    margin : 0 auto;

                }
            p{
                text-align :center
                position : absolute
                line-height : .44rem
                color : #333
                bottom : 0
                width : 100%
            }
</style>
