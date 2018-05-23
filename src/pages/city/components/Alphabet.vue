<template>
    <ul class="list">
        <li @touchstart='handleTouchStart'
            @touchmove='handleTouchMove'
            @touchend="handleTouchEnd"
            @click="handleLetterClick"
            v-for="item of letters"
            :key="item"
            class="item"
            :ref = "item"
        >{{item}}</li>
    </ul>
</template>
<script>
export default {
  name: 'alphabet',
  props: {
    list: {}
  },
  data () {
    return {
      touchStatus: false,
      startY: 0,
      timer: null
    }
  },
  updated () {
    this.startY = this.$refs['A'][0].offsetTop
  },
  computed: {
    letters () {
      const letters = []
      for (let i in this.list) {
        letters.push(i)
      }
      return letters
    }
  },
  methods: {
    handleLetterClick (e) {
      this.$emit('change', e.target.innerHTML)
    },
    handleTouchStart () {
      this.touchStatus = true
    },
    handleTouchMove (e) {
      if (this.touchStatus) {
        if (this.timer) {
          clearTimeout(this.timer)
        }
        this.timer = setTimeout(() => {
          const touchY = e.touches[0].clientY - 79
          const index = Math.floor((touchY - this.startY) / 20)
          if (index >= 0 && this.letters.length) {
            this.$emit('change', this.letters[index])
          } else if (index <= 23) {
            return false
          }
        }, 16)
      }
    },
    handleTouchEnd () {
      this.touchStatus = false
    }
  }
}
</script>
<style lang="stylus" scoped>
@import '~styles/varbless.styl';

.list {
  display: flex;
  flex-direction: column;
  justify-content: center;
  position: absolute;
  top: 1.58rem;
  right: 0;
  bottom: 0;
  width: 0.4rem;

  .item {
    text-align: center;
    line-height: 0.44rem;
    color: $bgColor;
  }
}
</style>
