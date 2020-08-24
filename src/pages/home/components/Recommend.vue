<template>
  <div class="recommend">
    <div class="recommend-title">热销推荐</div>
    <ul>
      <li class="recommend-item border-bottom" v-for="item of list" :key="item.id">
        <div class="item-img-wrapper">
          <img class="item-img" :src="item.imgUrl" alt="">
        </div>
        <div class="item-info">
          <p class="item-title">{{item.title}}</p>
          <p class="item-desc">{{item.desc}}</p>
          <button class="item-button">查看详情</button>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'HomeRecommend',
  props: {
    list: Array
  }
}
</script>

<style scoped lang="less">
@import url('~@/assets/styles/mixins.less');
.recommend {
  .recommend-title {
    margin-top: 0.2rem;
    line-height: 0.8rem;
    background: #eee;
    text-indent: 0.2rem;
  }
  .recommend-item {
    display: flex;
    overflow: hidden;
    height: 1.9rem;
    .item-img-wrapper {
      width: 1.7rem;
      height: 1.7rem;
      padding: 0.1rem;
      .item-img {
        display: block;
        width: 100%;
      }
    }
    .item-info {
      flex: 1;
      padding: .1rem;
      min-width: 0;// flex:1配合min-width:0保证内容在父盒子内，否则会超出父盒子，导致ellipsis不生效
      .item-title {
        line-height: .54rem;
        font-size: .32rem;
        .ellipsis();
      }
      .item-desc {
        line-height: .4rem;
        font-size: .20rem;
        color: #ccc;
        .ellipsis();
      }
      .item-button {
        margin-top: .2rem;
        background-color: #ff9300;
        padding: 0 .1rem;
        border-radius: .06rem;
        color: #fff;
      }
    }
  }
}
</style>
