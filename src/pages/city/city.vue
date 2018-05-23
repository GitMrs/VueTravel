<template>
    <div class="city">
      <CityHeader></CityHeader>
      <CitySearch :cities="cities"></CitySearch>
      <CityList :list="hotCities" :cities="cities" :Leter="Leter"></CityList>
      <CityAlphabet @change="handleLeterChange" :list="cities"></CityAlphabet>
    </div>
</template>
<script>
import CityHeader from './components/header'
import CitySearch from './components/citySearch'
import CityList from './components/cityList'
import CityAlphabet from './components/Alphabet'
import axios from 'axios'
export default {
  name: 'city',
  data () {
    return {
      hotCities: [],
      cities: {},
      Leter: ''
    }
  },
  components: {
    CityHeader,
    CitySearch,
    CityList,
    CityAlphabet
  },
  methods: {
    cityInfo () {
      axios.get('/api/city.json').then(this.CityData)
    },
    CityData (res) {
      res = res.data
      if (res.data) {
        const data = res.data
        console.log(data)
        this.hotCities = data.hotCities
        this.cities = data.cities
        console.log(this.cities)
      }
    },
    handleLeterChange (e) {
      this.Leter = e
    }
  },
  mounted () {
    this.cityInfo()
  }
}
</script>
<style lang="stylus" scoped>
</style>
