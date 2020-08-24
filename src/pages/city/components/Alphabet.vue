<template>
  <ul class="list">
    <li class="item" v-for="(item, key) of cities" :key="key">
      {{key}}
    </li>
  </ul>
</template>

<script>
export default {
  name: 'cityAlphabet',
  props: {
    cities: Object
  }
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
  right: .05rem;
  bottom: 0;
  width: 0.4rem;
  .item {
    line-height: 0.4rem;
    text-align: center;
    color: @bgColor;
  }
}
</style>
