<template>
  <ul class="list">
    <li class="item" v-for="item of letters" :key="item" :ref="item" @touchstart="handleTouchStart"
      @touchmove.prevent="handleTouchMove" @touchend="handleTouchEnd" @click="handleLetterClick">
      {{item}}
    </li>
  </ul>
</template>

<script>
export default {
  name: 'cityAlphabet',
  props: {
    cities: Object
  },
  computed: {
    letters () {
      const letters = []
      for (let i in this.cities) {
        letters.push(i)
      }
      return letters
    }
  },
  data () {
    return {
      touchStatus: false,
      startY: 0,
      timer: null
    }
  },
  updated () { // 当页面数据被更新, 且渲染完毕
    this.startY = this.$refs['A'][0].offsetTop
  },
  methods: {
    handleLetterClick (event) {
      this.$emit('change', event.target.innerText)
    },
    handleTouchStart () {
      this.touchStatus = true
    },
    handleTouchMove (event) {
      if (this.touchStatus) {
        if (this.timer) { // 节流
          clearTimeout(this.timer)
        }
        this.timer = setTimeout(() => {
          const touchY = event.touches[0].clientY - 79 // 高度是固定的
          const index = Math.floor((touchY - this.startY) / 20)// 每个字母高度20
          if (index >= 0 && index < this.letters.length) {
            this.$emit('change', this.letters[index])
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

<style scoped lang="less">
@import url("~@/assets/styles/varibles.less");
.list {
  display: flex;
  flex-direction: column;
  justify-content: center;
  position: absolute;
  top: 1.58rem;
  right: 0.05rem;
  bottom: 0;
  width: 0.4rem;
  .item {
    line-height: 0.4rem;
    text-align: center;
    color: @bgColor;
  }
}
</style>
