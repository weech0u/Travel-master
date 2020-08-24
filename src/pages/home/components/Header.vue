<template>
  <div class="header">
    <div class="header-left">
      <span class="iconfont back-icon">&#xe624;</span>
    </div>
    <div class="header-input">
      <span class="iconfont search-icon">&#xe632;</span>
      输入城市/景点
    </div>
    <router-link to="/city">
      <div class="header-right">
        {{this.city}}
        <span class="iconfont">&#xe64a;</span>
      </div>
    </router-link>
  </div>
</template>

<script>
export default {
  name: 'HomeHeader',
  props: {
    city: String
  }
}
</script>

<style scoped lang="less">
@import url("~@/assets/styles/varibles.less");
.header {
  display: flex;
  line-height: @headerHeight;
  background-color: @bgColor;
  color: #fff;
  .header-left {
    width: 0.64rem;
    float: left;
    text-align: center;
    .back-icon {
      font-size: 0.4rem;
    }
  }
  .header-input {
    flex: 1;
    line-height: 0.64rem;
    height: 0.64rem;
    margin-top: 0.12rem;
    margin-left: 0.2rem;
    background-color: #fff;
    border-radius: 0.1rem;
    color: #ccc;
    .search-icon {
      margin-left: 0.1rem;
    }
  }
  .header-right {
    width: 1.24rem;
    float: right;
    text-align: center;
    color: #fff;
  }
}
</style>
