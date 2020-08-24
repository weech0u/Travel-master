<template>
  <div class="wrapper">
    <swiper :options="swiperOption" v-if="showSwiper">
      <!-- slides -->
      <swiper-slide v-for="item in list" :key="item.id">
        <img class="swiper-img" :src="item.imgUrl">
      </swiper-slide>
      <!-- Optional controls -->
      <div class="swiper-pagination" slot="pagination"></div>
    </swiper>
  </div>
</template>

<script>
export default {
  name: 'HomeSwiper',
  props: {
    list: Array
  },
  data () {
    return {
      swiperOption: {
        pagination: '.swiper-pagination'
      }
    }
  },
  computed: {
    showSwiper () {
      return this.list.length
    }
  }
}
</script>

<style scoped lang="less">
.wrapper /deep/ .swiper-pagination-bullet-active {
  background-color: #fff !important;
}
.wrapper {
  width: 100%;
  height: 0; //相较于父级元素高度
  overflow: hidden;
  padding-bottom: 31.25%; //相较于宽度
  background-color: #eee;
  .swiper-img {
    width: 100%;
  }
}
</style>
