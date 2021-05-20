<template lang="html">
  <div class="container">
      <div class="card card-custom mb-3">
          <div class="card-body">
              <form class="" @submit.prevent="searchWeatherInfo">
              <div class="form-group">
                  <label for="city">Enter City Name</label>
                  <input type="text" class="form-control" name="" v-model="city">
              </div>
          </form>
          </div>
      </div>

      <div class="card card-custom">
          <div class="card-header">
              <h1 class="card-title h5 mb-0">Weather Report {{weather.name}} City</h1>
          </div>
          <div class="card-body">
              <div class="row">
                  <div class="col-md-4 text-center">
                      <p>Temperature</p>
                      <h2>{{temp()}}&deg;C</h2>
                      <img :src="icon" alt="weather icon">
                      <p>{{weather.weather[0].description}}</p>
                  </div>
                  <div class="col-md-4 text-center">
                      <p>Wind & Pressure</p>
                      <h4>Wind : {{weather.wind.speed}}m/s ({{weather.wind.deg}}&deg;)</h4>
                      <h4>Humidity : {{weather.main.humidity}}%</h4>
                      <h4>Pressure : {{weather.main.pressure}}hPa</h4>
                  </div>
                  <div class="col-md-4 text-center">
                      <p>Other</p>
                      <h4>Max Temp : {{Math.round(weather.main.temp_max - 273)}}&deg;C</h4>
                      <h4>Min Temp : {{Math.round(weather.main.temp_min - 273)}}&deg;C</h4>
                  </div>
              </div>
          </div>
      </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      city: "London",
      weatherAppKey : "950fba956f82992f9d0e7a9e3d35bfb4"
    }
  },
  computed: {
    icon() {
      return this.weather.weather ? `http://openweathermap.org/img/wn/${this.weather.weather[0].icon}.png` : ''
    }
  },
  head() {
    return {
      title: "Weather App",
      meta: [{
        hid: 'description',
        name: 'description',
        content: "This is Weather App Project"
      }]
    }
  },
  asyncData({
    params,
    $axios,
    $config: { apiSecret }
  }) {
    return $axios.$get(`https://api.openweathermap.org/data/2.5/weather?q=London&appid=${apiSecret}`)
      .then(res => {
        return {
          weather: res
        }
      })
  },
  methods: {
    searchWeatherInfo() {
      this.$axios.$get(`https://api.openweathermap.org/data/2.5/weather?q=${this.city}&appid=${this.$config.apiSecret}`)
        .then(res => (this.weather = res))
    },
    temp() {
      return Math.round(this.weather.main.temp - 273)
    }
  }
}
</script>

<style lang="css" scoped>
</style>
