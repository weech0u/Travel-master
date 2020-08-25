<template>
  <div>
    <detail-banner></detail-banner>
    <detail-header></detail-header>
    <detail-list :list='list'></detail-list>
    <div class='content'></div>
  </div>
</template>

<script>
import DetailBanner from './components/Banner'
import DetailHeader from './components/Header'
import DetailList from './components/List'
import axios from 'axios'
export default {
  name: 'Detail',
  components: {
    DetailBanner,
    DetailHeader,
    DetailList
  },
  data () {
    return {
      sightName: '',
      bannerImgs: [],
      gallaryImgs: [],
      list: []
    }
  },
  methods: {
    getDetailInfo () {
      var this_ = this
      axios.get('/api/detail.json?id', {
        params: {
          id: this.$route.params.id
        }
      })
        .then(function (res) {
          res = res.data
          var data = res.data
          if (res.ret) {
            this_.list = data.categoryList
            this_.sightName = data.sightName
          }
        })
    }
  },
  mounted () {
    this.getDetailInfo()
  }
}
</script>

<style scoped lang="less">
.content {
  height: 50rem;
}
</style>
