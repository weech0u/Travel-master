<template>
  <div class="header">
    城市选择
    <router-link to="/">
      <div class="iconfont header-back">&#xe624;</div>
    </router-link>
  </div>
</template>

<script>
export default {
  name: 'cityHeader'
}
</script>

<style scoped lang="less">
@import url("~@/assets/styles/varibles.less");
.header {
  position: relative;
  overflow: hidden;
  height: @headerHeight;
  line-height: @headerHeight;
  text-align: center;
  color: #fff;
  background-color: @bgColor;
  .header-back {
    position: absolute;
    width: 0.64rem;
    text-align: center;
    font-size: 0.4rem;
    top: 0;
    color: #fff;
  }
}
</style>
