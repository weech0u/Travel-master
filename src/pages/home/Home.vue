<template>
  <div>
    <home-header :city="city"></home-header>
    <home-swiper :list="swiperList"></home-swiper>
    <home-icons :list="iconList"></home-icons>
    <home-recommend :list="recommendList"></home-recommend>
    <home-weekend :list="weekendList"></home-weekend>
  </div>
</template>

<script>
import HomeHeader from './components/Header'
import HomeSwiper from './components/Swiper'
import HomeIcons from './components/icons'
import HomeRecommend from './components/Recommend'
import HomeWeekend from './components/Weekend'
import axios from 'axios'
export default {
  name: 'Home',
  components: {
    HomeHeader,
    HomeSwiper,
    HomeIcons,
    HomeRecommend,
    HomeWeekend
  },
  data () {
    return {
      city: '',
      swiperList: [],
      iconList: [],
      recommendList: [],
      weekendList: []
    }
  },
  methods: {
    getHomeInfo () {
      var this_ = this
      axios.get('/api/index.json')
        .then(function (res) {
          res = res.data
          if (res.ret && res.data) {
            var data = res.data
            this_.city = data.city
            this_.swiperList = data.swiperList
            this_.iconList = data.iconList
            this_.recommendList = data.recommendList
            this_.weekendList = data.weekendList
          }
        })
    }
  },
  mounted () {
    this.getHomeInfo()
  }
}
</script>

<style></style>
