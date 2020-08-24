<template>
    <div class="header">
        <div class="header-left">
          <span class="iconfont back-icon">&#xe624;</span>
        </div>
        <div class="header-input">
          <span class="iconfont search-icon">&#xe632;</span>
          输入城市/景点
        </div>
        <div class="header-right">
          城市
          <span class="iconfont">&#xe64a;</span>
        </div>
    </div>
</template>

<script>
export default {
  name: 'HomeHeader'
}
</script>

<style scoped lang="less">
@import url('~@/assets/styles/varibles.less');
.header {
    display: flex;
    line-height: .86rem;
    background-color: @bgColor;
    color: #fff;
    .header-left {
        width: 0.64rem;
        float: left;
        text-align: center;
        .back-icon {
          font-size: .4rem;
        }
    }
    .header-input {
        flex: 1;
        line-height: .64rem;
        height: .64rem;
        margin-top: .12rem;
        margin-left: .2rem;
        background-color: #fff;
        border-radius: .1rem;
        color: #ccc;
        .search-icon {
          margin-left: .1rem;
        }
    }
    .header-right {
        width: 1.24rem;
        float: right;
        text-align: center;
    }
}
</style>
