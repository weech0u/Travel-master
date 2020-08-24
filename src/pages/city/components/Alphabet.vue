<template>
  <ul class="list">
    <li class="item">A</li>
    <li class="item">A</li>
    <li class="item">A</li>
    <li class="item">A</li>
    <li class="item">A</li>
    <li class="item">A</li>
    <li class="item">A</li>
    <li class="item">A</li>
    <li class="item">A</li>
    <li class="item">A</li>
  </ul>
</template>

<script>
export default {
  name: 'cityAlphabet'
}
</script>

<style scoped lang="less">
@import url("~@/assets/styles/varibles.less");
.list {
  display: flex;
  flex-direction: column;
  justify-content: center;
  position: fixed;
  top: 1.58rem;
  right: 0;
  bottom: 0;
  width: .4rem;
  .item {
    line-height: .4rem;
    color: @bgColor;
  }
}
</style>
