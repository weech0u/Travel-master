<template>
  <div>
    <router-link tag="div" to="/" class="header-abs" v-show="showAbs">
      <span class="iconfont header-abs-back">&#xe624;</span>
    </router-link>
    <div class="header-fixed" v-show="!showAbs" :style="opacityStyle">
      <router-link to="/">
        <span class="iconfont header-fixed-back">&#xe624;</span>
      </router-link>
      景点详情
    </div>
  </div>
</template>

<script>
export default {
  name: 'DetailHeader',
  data () {
    return {
      showAbs: true,
      opacityStyle: {
        opacity: 0
      }
    }
  },
  methods: {
    handleScroll () {
      const top = document.documentElement.scrollTop
      if (top > 60) {
        var opacity = top / 140
        opacity = opacity > 1 ? 1 : opacity
        this.opacityStyle = {
          opacity
        }
        this.showAbs = false
      } else {
        this.showAbs = true
      }
    }
  },
  mounted () {
    window.addEventListener('scroll', this.handleScroll)
  },
  unmounted () { // 解绑全局事件
    window.removeEventListener('scroll', this.handleScroll)
  }
}
</script>

<style scoped lang="less">
@import url("~@/assets/styles/varibles.less");
.header-abs {
  position: absolute;
  border-radius: 0.4rem;
  background-color: rgba(0, 0, 0, 0.8);
  left: 0.2rem;
  top: 0.2rem;
  width: 0.8rem;
  height: 0.8rem;
  text-align: center;
  line-height: 0.8rem;
  .header-abs-back {
    color: #fff;
    font-size: 0.4rem;
  }
}
.header-fixed {
  position: fixed;
  z-index: 2;
  top: 0;
  left: 0;
  right: 0;
  height: @headerHeight;
  line-height: @headerHeight;
  text-align: center;
  color: #fff;
  background-color: @bgColor;
  .header-fixed-back {
    position: absolute;
    width: 0.64rem;
    text-align: center;
    font-size: 0.4rem;
    left: 0;
    color: #fff;
  }
}
</style>
