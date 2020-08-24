<template>
  <div>
    <city-header></city-header>
    <city-search></city-search>
    <city-list :cities="cities" :hot="hotCities"></city-list>
    <city-alphabet :cities="cities"></city-alphabet>
  </div>
</template>

<script>
import cityHeader from './components/Header'
import citySearch from './components/Search'
import cityList from './components/List'
import cityAlphabet from './components/Alphabet'
import axios from 'axios'
export default {
  name: 'City',
  components: {
    cityHeader,
    citySearch,
    cityList,
    cityAlphabet
  },
  data () {
    return {
      cities: {},
      hotCities: []
    }
  },
  methods: {
    getCityInfo () {
      var this_ = this
      axios.get('/api/city.json')
        .then(function (res) {
          res = res.data
          if (res.ret && res.data) {
            var data = res.data
            console.log(data)
            this_.cities = data.cities
            this_.hotCities = data.hotCities
          }
        })
    }
  },
  mounted () {
    this.getCityInfo()
  }
}
</script>

<style scoped lang="less">
</style>
